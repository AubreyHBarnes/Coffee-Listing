<script>
    let {data} = $props();
    // console.table(data)
    console.table( data.item)
</script>

<h1>getCoffee</h1>
<p>this is the getCoffee page.</p>

{#each data as { name, image }}
<p>{name}</p>
<img alt="" src="{image}" />

{/each}

<!-- <p>{data.item[0].name}</p> -->