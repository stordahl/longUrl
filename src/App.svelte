<script lang="ts">
	import Form from './components/Form.svelte';
</script>

<main>
	<h1>what if there was a url shortener that actually made your url...longer?</h1>
	<Form />
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>