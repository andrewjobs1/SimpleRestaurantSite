<script>
    import food from "$lib/assets/home-menu/food.jpg"
    import dessert from "$lib/assets/home-menu/dessert.jpg"
    import drink from "$lib/assets/home-menu/drink.png"
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
        
        element = document.querySelector("#home-section2")
        observer = new IntersectionObserver(callback, options)
        
        observer.observe(element)
    })
    
</script>

<div id="home-section2">
    <div class="grid md:grid-cols-3 py-10">
        {#key isVisible}
            <div in:fly={{y: 500, duration: 1500}} class="flex flex-col items-center p-3 gap-5">
                <h1 class="text-xl font-bold text-center text-primary-dark">
                    Food
                </h1>
                <div class="h-32 w-32 border rounded-full">
                    <img class="rounded-full" src={food} alt="Nepali Food">
                </div>
                <p class="leading-6 px-5 text-center">
                    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam dolor neque, condimentum quis ante ac, 
                    imperdiet varius sapien. Maecenas commodo ante et odio varius, at placerat mi tristique.
                </p>
                <a class="border-2 border-primary rounded-md py-2 px-4 text-md hover:bg-primary hover:text-text-primary" href="/menus">Menu</a>
            </div>
            <div  in:fly={{y: 500, duration: 1500}} class="flex flex-col items-center p-3 gap-5">
                <h1 class="text-xl font-bold text-center text-primary-dark">
                    Desserts 
                </h1>
                <div class="h-32 w-32 border rounded-full">
                    <img class="rounded-full" src={dessert} alt="Nepali Desserts">
                </div>
                <p class="leading-6 px-5 text-center">
                    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam dolor neque, condimentum quis ante ac, 
                    imperdiet varius sapien. Maecenas commodo ante et odio varius, at placerat mi tristique.
                </p>
                <a class="border-2 border-primary rounded-md py-2 px-4 text-md hover:bg-primary hover:text-text-primary" href="/menus">Menu</a>
            </div>
            <div  in:fly={{y: 500, duration: 1500}} class="flex flex-col items-center p-3 gap-5">
                <h1 class="text-xl font-bold text-center text-primary-dark">
                    Drinks
                </h1>
                <div class="h-32 w-32 border rounded-full">
                    <img class="rounded-full" src={drink} alt="Drinks">
                </div>
                <p class="leading-6 px-5 text-center">
                    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam dolor neque, condimentum quis ante ac, 
                    imperdiet varius sapien. Maecenas commodo ante et odio varius, at placerat mi tristique.
                </p>
                <a class="border-2 border-primary rounded-md py-2 px-4 text-md hover:bg-primary hover:text-text-primary" href="/menus">Menu</a>
            </div>
        {/key}
    </div>
</div>