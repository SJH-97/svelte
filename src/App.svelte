<script>
	let dogs = [
		// comment out data in array to see else block rendering
		{name: 'Cooper', age: 9, breed: 'French Bulldog', id: 1},
		{name: 'Marley', age: 9, breed: 'English Bulldog', id: 2},
		{name: 'Bailey', age: 5, breed: 'Pug', id: 3}
	];

	const handleClick = (id) => {
		// delete a dog from dogs
		dogs = dogs.filter((dog) => dog.id !== id);
	}

	let num = 21;
</script>

<!-- If Else statement with catch at bottom -->

{#if num > 20}
	<p>greater than 20</p>
{:else if num > 5}
	<p>greater than 5</p>
{:else} 
	<p>Not greater than 20 or 5</p>
{/if}

<main>
 {#each dogs as dog (dog.id)}
<div>
	<h4>{dog.name}</h4>
	<!-- if statement -->
	{#if dog.breed === 'French Bulldog'}
		<p>French bulldogs are the best</p>
	{/if}
	<p>{dog.age} years old, {dog.breed}</p>
	<!-- Inline handler -->
	<button on:click={() => handleClick(dog.id)}>
	Delete
	</button>
</div>
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