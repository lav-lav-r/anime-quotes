<script>
	import Quote from './components/Quote.svelte';
</script>

<main id="quote-box">
	<Quote/>
</main>

<style>
	:global(body) {
		height: 100vh;
		display: grid;
		place-content: center;
		background-color: #633F49;
		font-family: 'Rubik', sans-serif;
	}

	main {
		max-width: 90%;
		width: 620px;
		background-color: #69444E;
		box-shadow: 0 0 6px #1C1013;
		border-radius: 5px;
		padding: 2.25em 3em 2em 3em;

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