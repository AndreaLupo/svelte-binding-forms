<script>
    import CustomInput from "./CustomInput.svelte";
    import Toggle from "./Toggle.svelte";

    let val = 'Max';
    let price = 0;
    let selectedOption = 1;
    let agreed = false;
    let favColor = 'green';
    let singleFavColor = 'red';

    $:console.log(val);
    $:console.log(selectedOption);
    $:console.log(agreed);
    $:console.log(favColor);
    $:console.log(singleFavColor);

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

<input type="number" value={price}
    on:input={event => console.log(event.target.value)} />

<label>
    <input type="checkbox" bind:checked={agreed}>
    Agree to terms
</label>

<h1>Favourite color?</h1>
<label>
    <input type="radio" name="color" value="red" bind:group={favColor}>
    Red
</label>
<label>
    <input type="radio" name="color" value="green" bind:group={favColor}>
    Green
</label>
<label>
    <input type="radio" name="color" value="blue" bind:group={favColor}>
    Blue
</label>

<select bind:value={singleFavColor}>
    <option value="green">Green</option>
    <option value="red">Red</option>
    <option value="blue">Blue</option>
</select>