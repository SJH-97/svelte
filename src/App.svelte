<script>
	//importing Modal component 
	import Modal from './Modal.svelte';

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

	// Toggle Modal Function
	const toggleModal = () => {
		showModal = !showModal;
	}
	
	// Setting Show modal prop 
	let showModal = false;
</script>

<Modal isPromo {showModal} on:click={toggleModal}>
	<h3>Add a new dog</h3>
	<form>
		<input type="text" placeholder="Name">
		<input type="text" placeholder="Breed">
		<button>Add Dog</button>
	</form>
</Modal>
<main>
  <button on:click={toggleModal}>Open Modal</button>
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