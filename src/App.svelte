<script>
	 let name = "Samuel";
	 let belt = "Black";
	 const handleClick = () => {
		belt = "orange"
	 };
	 const handleInput = (e) => {
		belt = e.target.value
	 };
</script>

<main>
	<h1>Hello {name}!</h1>
	<h1 style="color: {belt}"> Belt colour: {belt}</h1>
	<button on:click={handleClick}>Update belt colour</button>
	 <!-- <input type="text" on:input={handleInput} value={belt}/> -->
	 <!-- Svelte two way binding using bind keyword -->
	 <input type="text" bind:value={belt} />
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