<script>
    import phone from "$lib/assets/icons/phone.png"
    import email from "$lib/assets/icons/email.png"
    import address from "$lib/assets/icons/address.png"
    import { fade, fly } from "svelte/transition"
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
        
        element = document.querySelector("#contact")
        observer = new IntersectionObserver(callback, options)
        
        observer.observe(element)
    })
    
</script>

{#key isVisible}    
    <div class="p-10 flex flex-col items-center gap-5" id="contact">
        <h1 class="font-semibold text-2xl text-primary">
            Contact us
        </h1>
        <div class="w-full grid grid-cols-1 md:grid-cols-2 justify-center md:gap-x-5 gap-y-10">
            <div>
                <iframe width="100%" title="Our location" src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3477.396507597179!2d-98.44991839021358!3d29.358677325172902!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x865cf7989fa8b88b%3A0x5f2331c60369766e!2s6835%20Pecan%20Valley%20Dr%2C%20San%20Antonio%2C%20TX%2078223%2C%20USA!5e0!3m2!1sen!2snl!4v1708068210016!5m2!1sen!2snl" height="350" style="border:0;" allowfullscreen="" loading="lazy" referrerpolicy="no-referrer-when-downgrade"></iframe>
            </div>
            <div>
                <ul class="flex flex-col gap-5 justify-center pl-20 text-menu-head">
                    <li class="flex gap-4 items-center">
                        <div class="cursor-pointer w-10 h-10 hover:animate-spin">
                            <img src={phone} alt="Twitter icon" class="object-cover">
                        </div>
                        <p in:fly={{x: 400, duration: 2000}}>
                            Phone: +1 (356) 434 5353
                        </p>
                    </li>
                    <li class="flex gap-4 items-center">
                        <div class="cursor-pointer w-10 h-10 hover:animate-spin">
                            <img src={email} alt="Twitter icon" class="object-cover">
                        </div>
                        <p in:fly={{x: 400, duration: 2000}}>
                            Email: nepalifood@gmail.com
                        </p>
                    </li>
                    <li class="flex gap-4 items-center">
                        <div class="cursor-pointer w-10 h-10 hover:animate-spin">
                            <img src={address} alt="Twitter icon" class="object-cover">
                        </div>
                        <p  in:fly={{x: 400, duration: 2000}}>
                            Lasses Blvd, Austin, Texas
                        </p>
                    </li>
                </ul>
            </div>
        </div> 
    </div>
{/key}