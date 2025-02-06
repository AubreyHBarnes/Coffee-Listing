<script>
    let { options, userChoice = $bindable(options[0].value) } = $props();
    
    const slugify = (str = "") => str.toLowerCase().replace(/ /g, "-").replace(/\./g, "");

    const uniqueID = Math.floor(Math.random() * 100)

    console.log(options[0])
</script>

<div role="radiogroup" aria-labelledby={`label-${uniqueID}`} class="productFilterWrapper mx-auto max-w-96 flex justify-center gap-6 pb-8" >

    {#each options as { value, label }}
    
        <input bind:group={userChoice} value={value} type="radio" id={slugify(label)} class="hidden-toggles__input hidden">
        <label for={slugify(label)} class="hidden-toggles__label p-4 rounded-xl">{label}</label>

     {/each}

</div>