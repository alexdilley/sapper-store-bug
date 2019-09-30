<script context="module">
  export const CTX = {};
</script>

<script>
  import { setContext } from 'svelte';
  import { writable } from 'svelte/store';
  import Nav from '../components/Nav.svelte';
  import { bar } from './_stores';

  export let segment;

  const foo = writable(0); // init

  setContext(CTX, foo);
</script>

<style>
	main {
		position: relative;
		max-width: 56em;
		background-color: white;
		padding: 2em;
		margin: 0 auto;
		box-sizing: border-box;
	}
</style>

<Nav {segment}/>

<main>
  <pre>_layout.svelte :: foo = {$foo}</pre>
  <pre>_layout.svelte :: bar = {$bar}</pre>
  <slot></slot>
</main>
