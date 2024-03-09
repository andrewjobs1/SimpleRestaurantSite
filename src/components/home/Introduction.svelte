<script>
    import { onMount } from "svelte"
    import { fly } from "svelte/transition"
    
    let animate = false

    onMount(() => {
        animate = true
    })


</script>


<div id="home-section1" class="bg-[url('$lib/assets/home-page.jpeg')] w-full h-auto bg-cover bg-center bg-no-repeat mb-8 md:h-screen flex justify-center items-center">
    <div>
        {#if animate}
            <h1 transition:fly={{x: 100, duration: 500}} class="text-text-primary text-4xl font-extrabold text-center">Save Your Spot</h1>
            <p transition:fly={{x: 100, duration: 500}} class="text-text-primary text-3xl font-bold text-center">Restaurant</p>
            <div transition:fly={{y: 400, duration: 1000}} class="flex justify-center mt-3">
                <a href="/booking" class="border-solid rounded-sm p-3 text-lg font-bold bg-button text-text-primary hover:bg-secondary hover:text-button">Book Now</a>
            </div>
        {/if} 
    </div>
</div>