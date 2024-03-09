<script>
    import { onMount } from "svelte"
    import { fly } from "svelte/transition"
    
    let animate = false

    onMount(() => {
        animate = true
    })


</script>
<div class="bg-[url('$lib/assets/about/about.jpg')] w-full h-64 bg-cover bg-center bg-no-repeat mb-8 md:h-screen flex justify-center items-center">
    <div>
        {#if animate}
            <div class="animate-bounce">
                <a href="#about-section2" transition:fly={{x: 100, duration: 500}} class="text-text-primary border-2 cursor-pointer rounded-md p-3 bg-primary text-4xl font-extrabold text-center">Learn About Us</a> 
            </div>
        {/if}
    </div>
</div>
<div id="about-section2" class="custom-grid px-32 py-16">
    <div class="">
        <h1 class="text-3xl font-semibold text-primary">
            Our History
        </h1>
        <p class="text-4xl">
            How we Started Our Restaurant
        </p>
    </div>
    <div class="flex flex-col gap-4">
        <p class="leading-7">
            Lorem ipsum dolor sit amet, consectetur adipiscing elit. Quisque porta iaculis nulla, 
            nec volutpat risus varius vitae. Vestibulum in semper lorem. Nunc nec augue quis felis 
            sagittis maximus. Sed elementum ante non semper fermentum. Donec dui urna, faucibus consectetur 
            ante id, condimentum fringilla arcu. Donec vitae accumsan justo, eget suscipit velit. Nam nec 
            auctor felis. Sed molestie nisi massa, a vulputate nibh posuere vel. Donec non ipsum ornare, 
            fringilla metus a, porttitor velit. In aliquet nec ligula ut semper. Maecenas ut justo lorem. 
            Vestibulum cursus enim molestie purus posuere, id luctus eros condimentum.
        </p>
        <p class="leading-7">
            Maecenas vel sem sed tellus tempus pretium et sed ipsum. Aliquam dictum, ipsum vitae dignissim 
            vestibulum, ex nibh feugiat dui, non iaculis neque ex eu augue. Aenean tristique faucibus quam, 
            non mollis ipsum aliquet sit amet. Fusce ac dictum metus, eget consectetur nulla. Morbi pretium 
            ornare risus, sed gravida orci consectetur sed. Nunc eu ipsum sapien. Suspendisse sagittis in libero 
            in lacinia.
        </p>
        <p class="leading-7">
            Donec in leo eget arcu pharetra tincidunt. Aenean eu augue venenatis, imperdiet nisl id, vestibulum metus. 
            Ut iaculis aliquet lacus, sagittis iaculis dui ornare et. Nullam sed sapien vitae erat efficitur sollicitudin. 
            Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; Nunc congue eros a 
            metus luctus pellentesque. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec pharetra ullamcorper tristique.
        </p>
    </div>
</div>

<style>
    .custom-grid {
        grid-template-columns: 1fr 3fr;
        display: grid;
        column-gap: 5rem;
    }

    @media (max-width: 768px) {
        .custom-grid {
            grid-template-columns: 1fr;
            row-gap: 4rem;
            padding: 5rem 4rem;
        }
    }
</style>