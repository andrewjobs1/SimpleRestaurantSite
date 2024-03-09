<script>
    import john from "$lib/assets/testimonials/John.jpg"
    import ravi from "$lib/assets/testimonials/ravi.jfif"
    import alice from "$lib/assets/testimonials/alice.jpg"
    import sam from "$lib/assets/testimonials/sam.jpg"
    import { fly } from 'svelte/transition'

    let arrayIndex = 0
    let ms = 10000
    let clear

    const changeArrayIndex = () => {
        arrayIndex += 1

        if (arrayIndex === testimonials.length - 1) {
            arrayIndex = 0
        }
    }
 
    $: {
	    clearInterval(clear)
	    clear = setInterval(changeArrayIndex, ms)
    }

    let testimonials = [
        {
            "name": "- John Doe",
            "review": `Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam dolor neque, condimentum quis ante ac, 
                        imperdiet varius sapien. Maecenas commodo ante et odio varius, at placerat mi tristique. Etiam et neque et magna finibus vestibulum.`,
            "src": john
        },
        {
            "name": "- Sam",
            "review": `Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam dolor neque, condimentum quis ante ac, 
                        imperdiet varius sapien. Maecenas commodo ante et odio varius, at placerat mi tristique. Etiam et neque et magna finibus vestibulum.`,
            "src": sam
        },
        {
            "name": "- Alice",
            "review": `Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam dolor neque, condimentum quis ante ac, 
                        imperdiet varius sapien. Maecenas commodo ante et odio varius, at placerat mi tristique. Etiam et neque et magna finibus vestibulum.`,
            "src": alice
        },
        {
            "name": "- Ravi",
            "review": `Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam dolor neque, condimentum quis ante ac, 
                        imperdiet varius sapien. Maecenas commodo ante et odio varius, at placerat mi tristique. Etiam et neque et magna finibus vestibulum.`,
            "src": ravi
        },
        {
            "name": "- Emily Wang",
            "review": `Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam dolor neque, condimentum quis ante ac, 
                        imperdiet varius sapien. Maecenas commodo ante et odio varius, at placerat mi tristique. Etiam et neque et magna finibus vestibulum.`,
            "src": alice
        }
    ]
</script>
<div class="py-24 bg-black text-text-primary">
    <div class="w-2/3 m-auto flex flex-col gap-7">
        <h2 class="text-center text-lg font-bold">TESTIMONIALS</h2>
        <h1 class="text-center text-3xl font-semibold">What Our Customers Say</h1>
        {#key arrayIndex}
            <div in:fly={{x: 100, duration: 1000}} class="flex flex-col items-center gap-5">
                <div class="rounded-full h-32 w-32 border-2 border-text-primary">
                    <img src={testimonials[arrayIndex].src} alt="customer profile" class="rounded-full">
                </div>
                <p class="leading-7 text-base text-center">
                    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam dolor neque, condimentum quis ante ac, imperdiet varius sapien. 
                    Maecenas commodo ante et odio varius, at placerat mi tristique. Etiam et neque et magna finibus vestibulum.
                </p>
                <p class="mt-5 text-center">{testimonials[arrayIndex].name}</p>
            </div>
        {/key}
    </div>
</div>