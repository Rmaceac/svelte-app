<script>
	let string = "friends";
	let greeting = "Bienvenido";
	let firstName = "";
	let lastName = "";
	let color = "orange";

	$: fullName = `${firstName} ${lastName}`



	const handleClick = () => {
		greeting = "Welcome"
	};

	const handleFirstInput = (e) => {
		firstName = e.target.value
	};

	const handleLastInput = (e) => {
		lastName = e.target.value
	};
</script>

<main>
	<h1 style="color: {color}">Hello {string}!</h1>
	<p>{greeting} {fullName}</p>
	<button on:click={handleClick}>Translate</button>
	<p>Enter your first name: </p>
	<input type="text" on:input={handleFirstInput}>
	<p>Enter your last name: </p>
	<input type="text" on:input={handleLastInput}>
	<p>Enter a colour: </p>
	<input type="text" on:input={(e) => {color = e.target.value}}>
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
