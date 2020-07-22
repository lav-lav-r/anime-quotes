<script>
	import Quote from './components/Quote.svelte';
</script>

<main id="quote-box">
	<Quote/>
</main>
<div class="info">
	<p><span class="tooltipText">🍵</span> <a href="https://www.rainfallproject.com/" target="_blank">Marcus Leonardo</a></p>
	<p>Powered by <a href="https://github.com/RocktimSaikia/anime-chan" target="_blank">Anime-chan</a></p>
</div>


<style>
	:global(:root) {
		--background: #FCFFF7;
		--accent: #E69173;
		--text: #E53D00;
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
		max-width: 720px;
		background-color: var(--background);
		box-shadow: 0 0 10px var(--accent);
		border-radius: 5px;
		padding: 2.25em 3em 2em 3em;

		display: grid;
		grid-template-columns: 1fr 1fr;
		grid-template-rows: repeat(2, auto);
	}

	.info {
		margin-top: .75rem;
		border: 1px solid var(--text);
		border-radius: 10px;
		cursor: help;

		display: flex;
		justify-content: space-between;
		align-items: baseline;
		padding: 0 1em 0 1em;
		height: .40rem;
		/* overflow: hidden; */
		transition: 200ms;

		position: relative;
		background-color: var(--text);
	}
	.info::before {
		content: "🞃";
		position: absolute;
		display: inline-block;
		transform: rotate(45deg);
		top: -11px;
		left: 50%;
		transform: translate(-50%);
		color: var(--background);
	}
	.info:hover {
		height: 2rem;
		background-color: var(--background);
		border: 2px solid var(--text);
	}
	.info > p {
		margin: .35em;
		opacity: 0;
		visibility: hidden;
		transition: opacity 100ms ease 100ms;
		transition: visibility 100ms ease 100ms;
	}
	.info:hover > p {
		opacity: 1;
		visibility: visible;
	}
	.info > p > a {
		text-decoration: none;
		color: var(--text);
		cursor: pointer;
	}
	.info > p:nth-child(2) > a {
		font-weight: bold;
	}

	.tooltipText {
		position: relative;
	}
	.tooltipText::before {
		position: absolute;
		content: "tea!";
		visibility: hidden;
		top: -35px;
		left: 50%;
		transform: translate(-50%);
		padding: .25em;
		background-color: var(--background);
		border: 2px solid var(--text);
		border-radius: 5px;
	}
	.tooltipText:hover::before {
		visibility: visible;

	}

	@media screen and (max-width: 768px) {
		main {
			max-width: 85%;
			margin: auto;
			padding: 1em;
		}
		.info {
			max-width: 85%;
			margin: .5em auto;
			height: 1rem;

			flex-direction: column;
			justify-content: center;
		}
		.info:hover {
			height: 4rem;
		}
	}
	
</style>