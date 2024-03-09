<script>
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
            threshold: 0.25
        };
        
        element = document.querySelector("#home-aboutus")
        observer = new IntersectionObserver(callback, options)
        
        observer.observe(element)
    })
    
</script>
<div class="mt-5 py-24 bg-primary-dark text-text-primary" id="home-aboutus">
    <div class="w-2/3 m-auto flex flex-col gap-7">
        <h2 class="text-center text-lg font-bold">ABOUT US</h2>
        <h1 class="text-center text-3xl font-semibold">Tradition and Passion</h1>
        {#key isVisible}     
            <p class="my-5 leading-8" in:fly={{x: 1000, duration: 2000}}>
                Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam dolor neque, condimentum quis ante ac, 
                imperdiet varius sapien. Maecenas commodo ante et odio varius, at placerat mi tristique. Etiam et neque et magna finibus vestibulum.
            </p>
            <div class="flex justify-center" in:fly={{y: 500, duration: 2000}}>
                <a href="/about" class="border-2 border-text-primary p-5 rounded-md hover:bg-text-primary hover:text-black">OUR STORY</a>
            </div>
        {/key}
    </div>
</div>