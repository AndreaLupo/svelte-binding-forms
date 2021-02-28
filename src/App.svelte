<script>
    import CustomInput from "./CustomInput.svelte";
    import Toggle from "./Toggle.svelte";

    let val = 'Max';
    let price = 0;
    let selectedOption = 1;

    $:console.log(val);
    $:console.log(selectedOption);

    function setValue(event) {
        val = event.target.value;
    }
</script>

<!-- <input type="text" value={val} on:input={setValue}/> -->

<!-- 2-way-binding -->
<!-- <input type="text" bind:value={val}> -->

<!-- bind:val - referes to the CustomInput val prop
    {val} - referes to the App val -->
<CustomInput bind:val={val}/>
<Toggle bind:chosenOption={selectedOption}/>

