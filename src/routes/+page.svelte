
<script>
    import Card from '$lib/components/Card/Card.svelte';
    let {data} = $props();
    console.log(data.item)
    
</script>
<img alt="" src="/img/bg-cafe-lg.jpg" />
<div class="floatingContainer px-4 py-8 md:p-[3rem] md:mx-[6rem] mb-[3rem] bg-[#111315] relative bottom-3 md:bottom-8 rounded-2xl text-white">
    <div class="headingCopyContainer m-auto max-w-xl text-center">
        <h1 class="text-4xl font-medium">Our Collection</h1>
        <p>Introducing our Coffee Collection, a selection of unique coffees from different roast types and origins,
             expertly roasted in small batches and shipped fresh&nbsp;weekly.</p>
    </div>
    <div class="CardGrid w-full max-md:mt-6 grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
        {#each data.item
            as { name, image, popular, price, rating, votes }}

            <Card
                coffeeName={name}
                coffeeImg={image}
                coffeePopular={popular}
                coffeePrice={price}
                coffeeRating={rating}
                coffeeVotes={votes}
            />
        {/each}
    </div>
</div>