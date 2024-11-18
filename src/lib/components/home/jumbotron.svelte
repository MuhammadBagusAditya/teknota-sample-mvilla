<script lang="ts">
	import { Button } from '$lib/components/ui/button';
	import Icon from '@iconify/svelte';
</script>

<section
	id="jumbotron"
	class="relative py-4 [background-image:_url('/banner.webp')] min-h-[80dvh] bg-no-repeat bg-cover bg-center bg-fixed after:absolute after:top-0 after:left-0 after:right-0 after:bottom-0 after:bg-slate-900/60 after:z-[1]"
>
	<div class="absolute top-0 left-0 w-full h-full z-[2] flex flex-col justify-center items-center">
		<h1 class="text-center text-4xl md:text-6xl font-bold text-slate-100 mb-4">MVilla</h1>

		<p class="text-center text-lg md:text-2xl text-slate-300 mb-8">
			Villa Terbaik di Gunung Merbabu
		</p>

		<Button class="py-2 px-4 md:py-6 md:px-8 md:text-lg rounded-full">Booking Sekarang</Button>
	</div>
</section>

<!-- <div
	class="w-[90%] sm:w-[80%] lg:w-[40%] bg-slate-50 shadow shadow-slate-900/20 rounded-lg translate-y-[-2rem] md:translate-y-[-50%] mx-auto relative z-[2] py-4 px-8 mb-[-2rem] grid grid-cols-1 md:grid-cols-3"
>
	<div class="flex flex-col items-center justify-center border-r border-slate-200 last:border-r-0">
		<Icon icon="mdi:alarm" class="text-6xl text-primary" />
		<h4 class="text-slate-800 text-xl font-semibold">Cepat</h4>
	</div>
	<div class="flex flex-col items-center justify-center border-r border-slate-200 last:border-r-0">
		<Icon icon="mdi:alarm" class="text-6xl text-primary" />
		<h4 class="text-slate-800 text-xl font-semibold">Cepat</h4>
	</div>
	<div class="flex flex-col items-center justify-center border-r border-slate-200 last:border-r-0">
		<Icon icon="mdi:alarm" class="text-6xl text-primary" />
		<h4 class="text-slate-800 text-xl font-semibold">Cepat</h4>
	</div>
</div> -->
