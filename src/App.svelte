<script>
	import Modal from './components/Modal.svelte';

	let string = "friends";
	let greeting = "Bienvenido";
	let firstName = "";
	let lastName = "";
	let color = "orange";

	$: fullName = `${firstName} ${lastName}`

	let people = [
		{name: "Brian", job: "cab driver", age: 39, id: 1},
		{name: "Sherri", job: "barber", age: 27, id: 2},
		{name: "Dylan", job: "comedian", age: 42, id: 3}
	]

	let showModal = false;

	const handleClick = () => {
		greeting = "Welcome"
	};

	const handleDelete = (id) => {
		people = people.filter(person => person.id != id)
	};

	const toggleModal = () => {
		showModal = !showModal;
	}
</script>

<Modal message="This is a message." isPromo={true} {showModal} on:click={toggleModal}/>
<main>
	<button on:click|once={toggleModal}>Show Modal</button>
	<h1 style="color: {color}">Hello {string}!</h1>
	<p>{greeting} {fullName}</p>
	<button on:click={handleClick}>Translate</button>
	<p>Enter your first name: </p>
	<input type="text" on:input={(e) => firstName = e.target.value}>
	<p>Enter your last name: </p>
	<input type="text" on:input={(e) => lastName = e.target.value}>
	<p>Enter a colour: </p>
	<input type="text" on:input={(e) => color = e.target.value}>

	<h3 style="color: {color}">A list of People:</h3>
	{#if people.length <= 2}
	<p>a couple of people...</p>
	{:else if people.length > 2}
	<p>a few people...</p>
	{/if}
	{#each people as person (person.id)}
		<p>{person.name} is a {person.job}. They are {person.age}.</p>
		<button on:click={() => handleDelete(person.id)}>delete person</button>
		{:else}
		<p>No people data available :/...</p>
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
