<script>
  import { onMount } from "svelte";
  import MenuItem from "./MenuItem.svelte";
  import { fly } from "svelte/transition";

  export let title
  export let items

  onMount(() => { 
    console.log(title)
  })
</script>
{#key items}
    <div class="my-10" in:fly={{x: 100, duration: 1000}}>
        <h1 class="text-xl font-semibold text-center text-primary">
            {title}
        </h1>
        <div class="grid grid-cols-1 md:grid-cols-2 w-2/3 m-auto justify-center items-center">
            {#each items as item}
                <MenuItem title={item.name} description={item.description} src={item.src}/>
            {/each} 
        </div>
    </div>
{/key}