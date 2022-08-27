<script>
	 let firstName = "Samuel";
	 let lastName = "Harrison";
	 let belt = "Black";

	//  reactive value
	$:fullName = `${firstName} ${lastName}`;

	// reactive statment
	$: {
		console.log(belt, "belt colour");
		console.log(fullName, "fullname");
		}
</script>

<main>
	<h1>{fullName} - {belt} belt</h1>
	 <!-- Svelte two way binding using bind keyword -->
	 <input type="text" bind:value={firstName} />
	 <input type="text" bind:value={lastName} />
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