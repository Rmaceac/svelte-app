<script>
	let string = "friends";
	let greeting = "Bienvenido";
	let name = "";
	let color = "orange"

	const handleClick = () => {
		greeting = "Welcome"
	};

	const handleInput = (e) => {
		name = e.target.value
	};
</script>

<main>
	<h1 style="color: {color}">Hello {string}!</h1>
	<p>{greeting} {name}</p>
	<button on:click={handleClick}>Translate</button>
	<p>Enter your name: </p>
	<input type="text" on:input={handleInput}>
	<p>Enter a colour: </p>
	<input type="text" bind:value={color}>
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
