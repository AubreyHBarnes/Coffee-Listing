
<script>
    import Card from '$lib/components/Card/Card.svelte';
    // import Toggle from '$lib/components/Toggle/Toggle.svelte';

    import { browser } from '$app/environment';

    let {data, available} = $props();

    console.log(data)

    if (browser) {
        let selection = document.getElementsByTagName('input');
        let radioButtons = Array.from(selection);
        radioButtons.forEach(option => {
            option.addEventListener('click', ()=> {
                let position = radioButtons.indexOf(event.target);
                
                if (radioButtons.indexOf(option) === 1) {
                    radioButtons[0].removeAttribute('checked')
                    event.target.setAttribute("checked", "")
                } else {
                    radioButtons[1].removeAttribute('checked')
                    event.target.setAttribute("checked", "")
                }

                available = event.target.id;
                
            })
        })
    }

    
    
</script>
<img alt="" src="/img/bg-cafe-lg.jpg" />
<div class="floatingContainer px-4 py-8 md:px-[4rem] lg:px-[6rem] md:mx-[6rem] mb-[3rem] bg-[#111315] relative bottom-3 md:bottom-[9rem] rounded-2xl text-white">
    <div class="headingCopyContainer m-auto max-w-[56ch] text-center py-8 bg-[url(/img/vector.svg)] bg-no-repeat bg-contain bg-right">
        <h1 class="text-4xl font-medium pb-4">Our Collection</h1>
        <p class="text-[#4d5562] font-medium">Introducing our Coffee Collection, a selection of unique coffees from different roast types and origins,
             expertly roasted in small batches and shipped fresh&nbsp;weekly.</p>
    </div>
    <div class="productFilterWrapper mx-auto max-w-96 flex justify-center gap-6 pb-8">
        <div>
            <input name="all-products" type="radio" id="all-products" class="hidden-toggles__input hidden" >
            <label for="all-products" class="hidden-toggles__label has-checked:bg-green-100 has-checked:bg-green-100 has-checked:border-green-700">All Products</label>
        </div>
        <div>
            <input name="available-now" type="radio" id="available-now" class="hidden-toggles__input hidden" >
            <label for="available-now" class="hidden-toggles__label has-[:checked]:bg-green-100 has-[:checked]:bg-green-100 has-[:checked]:border-green-700">Available Now</label>	
        </div>  

    </div>
    <div class="CardGrid w-full max-md:mt-6 grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6">
        {#each data.item
            as { id, name, image, popular, price, rating, votes }}
            <!-- {#if }
                
            {/if} -->
            <Card
                coffeeId={id}
                coffeeName={name}
                coffeeImg={image}
                coffeePopular={popular}
                coffeePrice={price}
                coffeeRating={rating}
                coffeeVotes={votes}
                coffeeFilter={available}
            />
        {/each}
    </div>
</div>



