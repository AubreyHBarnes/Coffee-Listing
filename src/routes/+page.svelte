
<script>
    import Card from '$lib/components/Card/Card.svelte';
    let {data} = $props();
    
</script>



<h1>Our Collection</h1>
<p>this is the home page.</p>

{#each data.item
    as { name, image }}

    <Card
        coffeeName={name}
        coffeeImg={image}
    />
{/each}