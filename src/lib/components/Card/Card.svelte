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
    <div class="cardRatingWrapper flex">
        {#if coffeeVotes}
            <img alt="" src="/img/Star_fill.svg" />
            <p class="font-medium">{coffeeRating} <span class="text-[#4d5562]">({coffeeVotes} votes)</span></p>
        {:else if !coffeeVotes}
            <img alt="" src="/img/Star.svg" />
            <p class="text-[#4d5562] font-medium">No Ratings</p>
        {:else}
            <p>No Data</p>
        {/if}
        {#if coffeeId===5}
            <p id="sold-out">Sold Out</p>
        {/if}
    </div>
</div>