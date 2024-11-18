<script lang="ts">
	import { scale } from 'svelte/transition';
	import Icon from '@iconify/svelte';
	import Separator from '$lib/components/ui/separator/separator.svelte';
	import { location } from '$lib/store';
	import { cn } from '$lib/utils';

	let screenYPos: number = $state(0);

	let isSidebarOpened: boolean = $state(false);
	let isTransparent: boolean = $derived($location === 'home' && screenYPos < 100);

	$effect(() => {
		if (isSidebarOpened) document.body.style.overflowY = 'hidden';
		else document.body.style.overflowY = 'auto';
	});

	$effect(() => {
		window.addEventListener('scroll', () => {
			screenYPos = window.scrollY;
		});
	});
</script>

<nav
	class={cn(
		'top-0 left-0 transition-all w-full z-[10] border-b border-slate-900/20',
		$location === 'home' ? 'fixed' : 'sticky',
		isTransparent ? 'bg-transparent' : 'bg-background'
	)}
>
	<div class="container py-3 lg:py-4 flex items-center gap-4 justify-between">
		<a
			href="/"
			class={cn('text-2xl font-bold', isTransparent ? 'text-slate-100' : 'text-slate-800')}
		>
			MVilla
		</a>

		<div class="hidden md:flex gap-6 items-center">
			<a
				href="/"
				class={cn(
					'after:bg-primary after:w-[0] after:transition-all hover:after:w-[2rem] after:h-[4px] after:rounded-full after:absolute after:bottom-[-0.5rem] after:left-[50%] after:translate-x-[-50%] after:block relative',
					isTransparent ? 'text-slate-200' : 'text-slate-700'
				)}>Beranda</a
			>
			<a
				href="#villas"
				class={cn(
					'after:bg-primary after:w-[0] after:transition-all hover:after:w-[2rem] after:h-[4px] after:rounded-full after:absolute after:bottom-[-0.5rem] after:left-[50%] after:translate-x-[-50%] after:block relative',
					isTransparent ? 'text-slate-200' : 'text-slate-700'
				)}>Daftar Villa</a
			>
			<a
				href="#offers"
				class={cn(
					'after:bg-primary after:w-[0] after:transition-all hover:after:w-[2rem] after:h-[4px] after:rounded-full after:absolute after:bottom-[-0.5rem] after:left-[50%] after:translate-x-[-50%] after:block relative',
					isTransparent ? 'text-slate-200' : 'text-slate-700'
				)}>Penawaran Spesial</a
			>
			<a
				href="#contacts"
				class={cn(
					'after:bg-primary after:w-[0] after:transition-all hover:after:w-[2rem] after:h-[4px] after:rounded-full after:absolute after:bottom-[-0.5rem] after:left-[50%] after:translate-x-[-50%] after:block relative',
					isTransparent ? 'text-slate-200' : 'text-slate-700'
				)}>Kontak Kami</a
			>
		</div>

		<button class="p-2 rounded-md inline-flex md:hidden" onclick={() => (isSidebarOpened = true)}>
			<Icon
				icon="mdi:menu"
				class={cn('text-2xl', isTransparent ? 'text-slate-100' : 'text-slate-800')}
			/>
		</button>
	</div>
</nav>

{#if isSidebarOpened}
	<div
		class="fixed top-0 left-0 right-0 bottom-0 z-[11] bg-slate-900/70 transition-all flex justify-center items-center"
		transition:scale={{ duration: 100 }}
	>
		<div class="bg-primary py-4 px-6 rounded-lg text-primary-foreground w-[90%] h-[90%]">
			<div class="flex items-center justify-between gap-4">
				<h3 class="text-xl">Menu</h3>

				<button class="p-2 rounded-md" onclick={() => (isSidebarOpened = false)}>
					<Icon icon="mdi:close" class="text-xl" />
				</button>
			</div>

			<Separator class="bg-primary-foreground my-2" />
		</div>
	</div>
{/if}
