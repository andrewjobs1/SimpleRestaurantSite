<script>
    export let title
    export let description
    export let src
</script>
<div class="flex flex-col">
    <div class="mt-5 flex items-center gap-4">
        <div class="h-16 w-16 rounded-full">
            <img src={src} class="rounded-full object-cover" alt="Food">
        </div>
        <div>
            <h1 class="font-semibold text-menu-head">
                {title}
            </h1>
        </div>
    </div>
    <p class="p-5">
        {description}
    </p>
</div>