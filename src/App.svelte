<script>
	import Quote from './components/Quote.svelte';
</script>

<main id="quote-box">
	<Quote/>
</main>

<style>
	:global(:root) {
		--background: #69444E;
		--accent: #1C1013;
		--text: #333333;
	}
	:global(body) {
		margin: 0;
		padding: 0;
		box-sizing: border-box;

		height: 100vh;
		display: grid;
		place-content: center;
		
		font-family: 'Rubik', sans-serif;
		background-color: var(--background);
		color: var(--text);
	}

	main {
		max-width: 90%;
		width: 550px;
		background-color: var(--background);
		box-shadow: 0 0 6px var(--accent);
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