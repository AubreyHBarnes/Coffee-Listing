
<script>
    let {data} = $props();
    console.log(data.item)
</script>

<h1>Our Collection</h1>
<p>this is the home page.</p>

{#each data.item
    as { name, image }}
<p>{name}</p>
<img alt="" src="{image}" />

{/each}