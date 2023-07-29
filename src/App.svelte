<script>
	let string = "friends";
	let greeting = "Bienvenido";
	let name = "";

	const handleClick = () => {
		greeting = "Welcome"
	};

	const handleInput = (e) => {
		name = e.target.value
	};
</script>

<main>
	<h1>Hello {string}!</h1>
	<p>{greeting} {name}</p>
	<button on:click={handleClick}>Translate</button>
	<input type="text" on:input={handleInput}>
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
