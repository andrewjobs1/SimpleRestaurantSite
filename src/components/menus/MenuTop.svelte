<script> 
    import { onMount } from "svelte"
    import { fly } from "svelte/transition"
    
    let animate = false

    onMount(() => {
        animate = true
    })

</script>
{#if animate}
    <div class="h-64 flex justify-center items-center bg-[url('$lib/assets/menus/title.jpg')]">
        <h1 transition:fly={{x: 400, duration: 1000}} class="font-extrabold text-5xl md:text-9xl text-primary-dark">
            MENUS
        </h1>
    </div>
{/if}