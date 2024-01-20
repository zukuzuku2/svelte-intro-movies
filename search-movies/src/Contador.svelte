<script>
	// Esto seria una prop que para que funcione hay siempre que exportar y desde el otro componente entonces hacer uso de el
	export let counter = 0

	function Incrementar() {
		counter++
	}
	function Disminuir() {
        counter === 0 ? counter = 0 : counter--;
	}

	// Declaraciones Reactiva para que cambie siempre que se refresque la pagina o como un estado creo yo
	$: esParOImpar = counter % 2 === 0 ? ' Es par' : ' Es impar'
	$: if (counter > 9) {
		
			counter = 9
		
	}

</script>

<!-- <main>
	<button on:click={Incrementar}>Incrementar</button>
	<span class='span'>{counter}{esParOImpar}</span>
	<button on:click={Disminuir}>Disminuir</button>
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
	
	.span{
		width: 300px;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>

