<script>
	import Quote from './components/Quote.svelte';
</script>

<main id="quote-box">
	<Quote/>
</main>
<div class="info">
	<p class="">🍵 Marcus Leonardo</p>
	<p class="">Powered by <a href="#">Api Name</a></p>
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
		max-width: 550px;
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
		cursor: pointer;

		display: flex;
		justify-content: space-between;
		padding: 0 1em 0 1em;
		height: .50rem;
		overflow: hidden;
		transition: 200ms;

		position: relative;
		background-color: var(--text);
	}
	.info::before {
		content: "🞃";
		position: absolute;
		display: inline-block;
		transform: rotate(45deg);
		top: -10px;
		left: 50%;
		transform: translate(-50%);
		color: var(--background);
	}
	.info:hover {
		height: 3rem;
		background-color: var(--background);
		border: 2px solid var(--text);
	}

	@media screen and (max-width: 768px) {
		main {
			max-width: 85%;
			margin: auto;
			padding: 1em;
		}
	}
</style>