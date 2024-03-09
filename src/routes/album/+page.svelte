<div class="w-3/5 mx-auto my-4">
    {#each maindata as sources}
        <Photo sources={sources}/>
    {/each}
</div>
<script>
    import Photo from "../../components/album/Photo.svelte";
    import album1 from "$lib/assets/album/album1.jpeg"
    import album2 from "$lib/assets/album/album2.jpg"

    let maindata = [
                    [
                        album1,
                        album2
                    ],
                    [
                        album1, 
                        album2 
                    ],
                    [
                        album1,
                        album2 
                    ],
                    [
                        album1,
                        album2 
                    ],
                    [
                        album1,
                        album2 
                    ]
                ]
</script>