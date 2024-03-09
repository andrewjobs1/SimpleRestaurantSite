<script>
    import facebook from "$lib/assets/icons/facebook.png"
    import instagram from "$lib/assets/icons/instagram.png"
    import twitter from "$lib/assets/icons/twitter.png"
</script>
<div class="text-text-primary">
    <div class="bg-primary-dark p-10">
        <div class="text-center font-bold">LOGO</div>
        <div class="grid grid-cols-1 gap-x-10 justify-evenly mt-7 md:grid-cols-3 sm:grid-cols-2 gap-y-10">
            <div>
                <h1 class="border-b-4 border-primary font-semibold">OPENING HOURS</h1>
                <ul class="flex flex-col py-2 gap-2">
                    <li>Open daily from 8am</li>
                    <li>Breakfast: Daily from 8am - 11am</li>
                    <li>Lunch: Daily from 12pm - 3pm</li>
                    <li>Dinner: Daily from 6pm - 12pm</li>
                </ul>
            </div>
            <div>
                <h1 class="border-b-4 border-primary font-semibold">LOCATION</h1>
                <ul class="flex flex-col p-2 gap-2">
                    <li>Traditional Nepali Restaurant</li>
                    <li>Lasses Blvd</li>
                    <li>Austin, Texas</li>
                    <li>USA</li>
                </ul>
            </div>
            <div>
                <h1 class="border-b-4 border-primary font-semibold">FOLLOW US</h1> 
                <ul class="flex gap-5 items-center pt-5">
                    <li class="cursor-pointer w-8 h-8 hover:animate-spin">
                        <img src={facebook} alt="facebook icon" class="object-cover">
                    </li>
                    <li class="cursor-pointer w-8 h-8 hover:animate-spin">
                        <img src={instagram} alt="Instagram icon" class="object-cover">
                    </li>
                    <li class="cursor-pointer w-8 h-8 hover:animate-spin">
                        <img src={twitter} alt="Twitter icon" class="object-cover">
                    </li>
                </ul>
            </div>
        </div>
    </div>
    <div class="bg-primary py-8 text-center">
        <p>© 2018 Traditional Nepali Restaurant. All rights reserved.</p>
        <p>Design & Development by PictureElement (Prabesh Bimali).</p>
    </div>
</div>