<script>
  import { getContext } from 'svelte'
  import { CTX } from './_layout.svelte';
  import { bar } from './_stores';

  const foo = getContext(CTX);
  foo.update(i => i + 1);
  bar.set(2); // init
</script>

<style>
	h1, figure, p {
		text-align: center;
		margin: 0 auto;
	}

	h1 {
		font-size: 2.8em;
		text-transform: uppercase;
		font-weight: 700;
		margin: 0 0 0.5em 0;
	}

	figure {
		margin: 0 0 1em 0;
	}

	img {
		width: 100%;
		max-width: 400px;
		margin: 0 0 1em 0;
	}

	p {
		margin: 1em auto;
	}

	@media (min-width: 480px) {
		h1 {
			font-size: 4em;
		}
	}
</style>

<svelte:head>
	<title>Sapper project template</title>
</svelte:head>

<pre>routes/index.svelte :: $foo = {$foo}</pre>
<pre>routes/index.svelte :: $bar = {$bar}</pre>
<h1>Great success!</h1>

<figure>
	<img alt='Borat' src='great-success.png'>
	<figcaption>HIGH FIVE!</figcaption>
</figure>

<p><strong>Try editing this file (src/routes/index.svelte) to test live reloading.</strong></p>

<button on:click={() => foo.update(i => i + 1)}>update foo</button>
<button on:click={() => bar.update(i => i + 1)}>update bar</button>
