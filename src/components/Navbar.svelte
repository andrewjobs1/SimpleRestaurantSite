<script>
    import { page } from "$app/stores"
    import facebook from "$lib/assets/icons/facebook.png"
    import instagram from "$lib/assets/icons/instagram.png"
    import twitter from "$lib/assets/icons/twitter.png"
    let isMenuOpen = false;

    function toggleMenu() {
        isMenuOpen = !isMenuOpen;
    }
</script>

<style>
    /* Add any custom styles here */
</style>

<div class="flex p-5 justify-between bg-primary text-text-primary font-bold sticky top-0 items-center">
    <div class="flex gap-10 items-center">
        <div>
            Logo
        </div>
        <!-- Conditionally render the menu based on the isMenuOpen state -->
    <!-- Always display the social icons -->
    <ul class="flex gap-5 items-center">
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
    <!-- Update the button to toggle the menu -->
    <button class="md:hidden" on:click={toggleMenu}>
        <div class="transition ease-in-out border-b-4 w-6 {isMenuOpen ? "translate-y-2 rotate-45": ""}"></div>
        <div class="transition ease-in-out border-b-4 w-6 mt-1 {isMenuOpen ? "scale-0": ""}"></div>
        <div class="border-b-4 w-6 mt-1 {isMenuOpen ? "-translate-y-2 -rotate-45": ""}"></div>
    </button>
        <ul class="md:flex md:flex-row md:gap-5 hidden"> 
            <li>
                <a href="/" class="{$page.route.id === "/"? "text-nav-active": "text-text-primary"} hover:text-nav-active">
                    Home
                </a>
            </li>
            <li>
                <a href="/menus" class="{$page.route.id === "/menus" ? "text-nav-active": "text-text-primary"} hover:text-nav-active">
                    Menus
                </a>
            </li>
            <li>
                <a href="/about" class="{$page.route.id === "/about" ? "text-nav-active": "text-text-primary"} hover:text-nav-active">
                    About
                </a>
            </li>
            <li>
                <a href="/album" class="{$page.route.id === "/album" ? "text-nav-active": "text-text-primary"} hover:text-nav-active">
                    Album
                </a>
            </li>
            <li>
                <a href="/booking" class="{$page.route.id === "/booking" ? "text-nav-active": "text-text-primary"} hover:text-nav-active">
                    Reservations
                </a>
            </li>
            <li>
                <a href="/#contact">
                    Contact
                </a>
            </li>
        </ul>
</div>
<ul class="md:hidden flex-col md:gap-5 flex bg-primary text-text-primary font-semibold items-center {isMenuOpen? "": "hidden"} py-4 gap-3 sticky top-16"> 
    <li>
        <a href="/" on:click={toggleMenu} class=" hover:text-nav-active">
            Home
        </a>
    </li>
    <li>
        <a href="/menus" on:click={toggleMenu} class=" hover:text-nav-active">
            Menus
        </a>
    </li>
    <li>
        <a href="/about" on:click={toggleMenu} class=" hover:text-nav-active">
            About
        </a>
    </li>
    <li>
        <a href="/album" on:click={toggleMenu} class=" hover:text-nav-active">
            Album
        </a>
    </li>
    <li>
        <a href="/booking" on:click={toggleMenu} class=" hover:text-nav-active">
            Reservations
        </a>
    </li>
    <li>
        <a href="#contact" on:click={toggleMenu} class=" hover:text-nav-active">
            Contact
        </a>
    </li>
</ul>