<script>
    let {coffeeName, coffeeImg,  coffeePopular, coffeePrice, coffeeRating, coffeeVotes} = $props();
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
    <div class="cardRatingWrapper">
        <img alt="" src="" />
        {#if coffeeVotes}
            <p>ratings</p>
        {/if}
    </div>
</div>