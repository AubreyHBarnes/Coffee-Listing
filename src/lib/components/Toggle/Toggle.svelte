<script>
    let { options, userChoice = $bindable(options[0].value) } = $props();
    // let userChoice = $state(options[0].value);

    const slugify = (str = "") => str.toLowerCase().replace(/ /g, "-").replace(/\./g, "");
</script>

<div role="radiogroup" class="productFilterWrapper mx-auto max-w-96 flex justify-center gap-6 pb-8" >

    {#each options as { value, label }}
    
        <input bind:group={userChoice} value={value} type="radio" id={slugify(label)} class="hidden-toggles__input hidden " >
        <label for={slugify(label)} class="hidden-toggles__label p-4 rounded-xl">{label}</label>
    
        <!-- <input bind:group={userChoice} value={value} name="available-now" type="radio" id="available-now" class="hidden-toggles__input hidden" >
        <label for="available-now" class="hidden-toggles__label has-[:checked]:bg-green-100 has-[:checked]:bg-green-100 has-[:checked]:border-green-700">Available Now</label>	 -->
     {/each}

</div>