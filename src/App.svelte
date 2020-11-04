<script lang="ts">
	import Router from 'svelte-spa-router';
	import { link } from 'svelte-spa-router';
	import active from 'svelte-spa-router/active';

	import Home from './Home.svelte';
	import Thing from './Thing.svelte';
	export let name: string;

	let routes = {
		'/': Home,
		'/thing': Thing
	}
</script>

<main>
	<h1>Hello {name}!</h1>

	<a use:link use:active href="/">Home</a>
	<a use:link use:active href="/thing">Thing</a>

	<p></p>

	<Router {routes}/>
</main>

<style>
	:global(a.active) {
    color: red;
	}

	a {
		display: block;
	}

	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>