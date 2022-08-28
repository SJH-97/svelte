<script>
    import { createEventDispatcher } from 'svelte';

    let dispatch = createEventDispatcher();

    let name;
    let breed;
    let age;
    let skills = [];
    const handleSubmit = () => {
        const dog = {
            name,
            breed,
            age,
            skills,
            id: Math.random()
        };
        dispatch(addDog, dog);
    }
</script>

<form on:submit|preventDefault={handleSubmit}>
    <input type="text" placeholder="name" bind:value={name}>
    <input type="number" placeholder="age" bind:value={age}>
    <label for="skills">Skills:</label>
        <input type="checkbox" bind:group={skills} value="tricks">tricks<br>
        <input type="checkbox" bind:group={skills} value="speedy">speedy<br>
        <input type="checkbox" bind:group={skills} value="brave">brave<br>
    <select for="breed" bind:value={breed}>
        <option value="french bulldog">french bulldog</option>
        <option value="enlish bulldog">english bulldog</option>
        <option value="french bordeaux">french bordeaux</option>
        <option value="pug">pug</option>
    </select>
    <button>Add Dog</button>
</form>

<style>

</style>