<script>
    let {coffeeId, coffeeName, coffeeImg,  coffeePopular, coffeePrice, coffeeRating, coffeeVotes } = $props();

</script>

<div class="cardWrapper">
    <div class="cardImgWrapper">
        {#if coffeePopular === true}
            <p class="absolute mx-2 my-2 px-2 py-1 bg-yellow-400 rounded-xl text-black text-xs font-medium">Popular</p>
        {/if}
        <img class="rounded-xl w-full" alt="" src="{coffeeImg}" />
    </div>
    <div class="cardPriceWrapper flex justify-between pt-2">
        <p class="text-white font-medium">{coffeeName}</p>
        <span class="text-black bg-[#FEF7EE] rounded-md px-2 py-1 font-medium text-sm h-min">{coffeePrice}</span>
    </div>
    <div class="cardRatingWrapper flex items-center justify-between">
        <div class="score-votes flex items-center">
            {#if coffeeVotes}
                <img alt="" src="/img/Star_fill.svg" />
                <p class="text-md font-medium">{coffeeRating} <span class="text-[#4d5562] pl-1">({coffeeVotes} votes)</span></p>
            {:else if !coffeeVotes}
                <img alt="" src="/img/Star.svg" />
                <p class="text-[#4d5562] text-small">No Ratings</p>
            {:else}
                <p>No Data</p>
            {/if}
        </div>
        
        {#if coffeeId===5}
            <p id="sold-out" class="text-[#ED735D] font-medium text-sm">Sold Out</p>
        {/if}
    </div>
</div>