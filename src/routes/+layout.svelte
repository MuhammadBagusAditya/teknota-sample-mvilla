<script lang="ts">
	import '../app.css';
	import Loader from '$lib/components/loader.svelte';
	import Navbar from '$lib/components/navbar.svelte';

	import { location } from '$lib/store';

	let { children } = $props();
</script>

<!-- {#if $location !== 'home'} -->
<Navbar />
<!-- {/if} -->

<main>
	{@render children()}
</main>

<Loader />
