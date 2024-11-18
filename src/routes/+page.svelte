<script lang="ts">
	import Jumbotron from '$lib/components/home/jumbotron.svelte';
	import Villas from '$lib/components/home/villas.svelte';
	import Offers from '$lib/components/home/offers.svelte';
	import Contacts from '$lib/components/home/contacts.svelte';
	import { location } from '$lib/store';

	location.set('home');
</script>

<svelte:head>
	<title>MVilla: Villa terbaik di Gunung Merbabu</title>
</svelte:head>

<Jumbotron />
<Villas />
<Offers />
<Contacts />
