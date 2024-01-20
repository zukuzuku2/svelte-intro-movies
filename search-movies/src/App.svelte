<script>
	import Contador from "./Contador.svelte";
	import Input from "./Input.svelte";
	// Esto seria una prop
	export let name;
	export let counter = 0

	function handleClick() {
		name = 'otro nombre'
	}

</script>

<!-- <main>
	<Contador/>
	<Input/>
</main> -->

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	button{
		text-align: center;
	}

	h1 {
		color: #09f;
		text-transform: uppercase;
		font-size: 32px;
		font-weight: 100;
	}

	section{
		align-items: center;
		display: flex;
		flex-direction: column;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>

<section>
	<h1>Search movies</h1>
	<Input/>
</section>