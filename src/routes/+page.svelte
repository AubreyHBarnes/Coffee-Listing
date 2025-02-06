
<script>
    import Card from '$lib/components/Card/Card.svelte';
    import Toggle from '$lib/components/Toggle/Toggle.svelte';
    
    let {data} = $props(); //data is coming from +page.server.js

    let fullCatalog = Array.from(data.item); //Array.from since we are receiving an object full of objects.
    let filteredCatalog = fullCatalog.filter(coffee => coffee.id !== 5); 

    

    const options = [{
		value: 'all-products',
		label: 'All Products',
	}, {
		value: 'available-now',
		label: 'Available Now',
	}, ]

    let radioValue = $state(options[0].value); //default radio choice
  
</script>

<svelte:head>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=DM+Sans:ital,opsz,wght@0,9..40,100..1000;1,9..40,100..1000&display=swap" rel="stylesheet">
    <title>Aubrey Barnes Coffee Listing</title>
</svelte:head>
<img alt="" src="/img/bg-cafe-lg.jpg" />
<div class="floatingContainer px-4 py-8 md:px-[4rem] lg:px-[6rem] md:mx-[6rem] mb-[3rem] bg-[#111315] relative bottom-3 md:bottom-[9rem] rounded-2xl text-white">
    <div class="headingCopyContainer m-auto max-w-[56ch] text-center py-8 bg-[url(/img/vector.svg)] bg-no-repeat bg-contain bg-right">
        <h1 class="text-4xl font-medium pb-4">Our Collection</h1>
        <p class="text-[#4d5562] font-medium">Introducing our Coffee Collection, a selection of unique coffees from different roast types and origins,
             expertly roasted in small batches and shipped fresh&nbsp;weekly.</p>
    </div>
    
    <Toggle {options} bind:userChoice={radioValue}/>

    <div class="CardGrid w-full max-md:mt-6 grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
        {#if radioValue === "" || radioValue === 'all-products'}
            {#each fullCatalog
                as { id, name, image, popular, price, rating, votes }}
            
                <Card
                    coffeeId={id}
                    coffeeName={name}
                    coffeeImg={image}
                    coffeePopular={popular}
                    coffeePrice={price}
                    coffeeRating={rating}
                    coffeeVotes={votes}
                    
                />  
            {/each}
        {:else}
            {#each filteredCatalog
                as { id, name, image, popular, price, rating, votes }}
            
                <Card
                    coffeeId={id}
                    coffeeName={name}
                    coffeeImg={image}
                    coffeePopular={popular}
                    coffeePrice={price}
                    coffeeRating={rating}
                    coffeeVotes={votes}
                    
                />  
            {/each}    
        {/if}
    </div>
</div>



