<script>
	import Quote from './components/Quote.svelte';
</script>

<main>
	<Quote/>
</main>

<style>
	:global(body) {
		height: 100vh;
		display: grid;
		place-content: center;
		background-color: #633F49;
	}

	main {
		max-width: 90%;
		width: 720px;
		background-color: #69444E;
		box-shadow: 0 0 6px #1C1013;
		border-radius: 5px;
		padding: 1em 1em .10em 1em;

		display: grid;
		grid-template-columns: 1fr 1fr;
		grid-template-rows: repeat(2, auto);
	}


	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>