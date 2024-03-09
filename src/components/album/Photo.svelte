<script>
    export let sources
    import { fly } from "svelte/transition"
    import { onMount } from "svelte" 

    let isVisible = false

    let options
    let element 
    let observer

    const callback = (entries, observer) => {
        entries.forEach(entry => {
            if (entry.intersectionRatio > 0) {
                isVisible = true
            } else {
                isVisible = false
            }
        })
    }
    
    onMount(() => {
        options = {
            root: null,
            rootMargin: "0px",
            threshold: 0.05
        };
        
        element = document.querySelector(".photo-wrapper")
        observer = new IntersectionObserver(callback, options)
        
        observer.observe(element)
    })

    $: {
        console.log(isVisible)
    }
    
</script>
<div class="grid grid-cols-1 md:grid-cols-2 gap-y-4 gap-x-4 my-3">
    {#key isVisible}
        <div in:fly={{x: -1000, duration: 2000}}  class="w-full h-full photo-wrapper">
            <img class="block h-full w-full rounded-lg object-cover object-center" src={sources[0]} alt="Nepali food">
        </div>
        <div in:fly={{x: 1000, duration: 2000}} class="w-full h-full photo-wrapper">
            <img class="block h-full w-full rounded-lg object-cover object-center" src={sources[1]} alt="Nepali food">
        </div>
    {/key}
</div>