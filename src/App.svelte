<script>
	let dogs = [
		// comment out data in array to see else block rendering
		{name: 'Cooper', age: 9, breed: 'French Bulldog', id: 1},
		{name: 'Marley', age: 9, breed: 'English Bulldog', id: 2},
		{name: 'Bailey', age: 5, breed: 'Pug', id: 3}
	];
</script>

<main>
 {#each dogs as dog (dog.id)}
	<h4>{dog.name}</h4>
	<p>{dog.age} years old, {dog.breed}</p>
 {:else}
	<p>There are no dogs in the dogs array</p>
 {/each}
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>