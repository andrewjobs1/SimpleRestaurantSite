<script>
  import "../app.css";
  import Footer from "../components/Footer.svelte";
  import Navbar from "../components/Navbar.svelte";
</script>

<div class="font-roboto">
    <Navbar/>
    <slot />
    <Footer/>
</div>