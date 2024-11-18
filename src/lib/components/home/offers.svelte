<script lang="ts">
	import { Trigger as DialogTrigger, Root as DialogRoot } from '$lib/components/ui/dialog';
	import OfferDialog from '$lib/components/offer-dialog.svelte';
	import { offers } from '$lib/data.json';

	let offerDetails: OfferDetail = $state({
		name: '',
		price: 0,
		features: [],
		img: ''
	});
</script>

<section id="offers">
	<div class="container py-8">
		<h2 class="text-2xl md:text-3xl font-bold mb-8 text-slate-800 text-center">
			Penawaran Spesial Kami
		</h2>

		<!-- <DialogRoot> -->
		<div class="grid grid-cols-1 lg:grid-cols-2 gap-4">
			{#each offers as offer}
				<!-- <DialogTrigger onclick={() => (offerDetails = offer)}> -->
				<div
					class="relative aspect-video overflow-hidden w-full transition-all active:scale-[.98] cursor-pointer after:absolute after:top-0 after:left-0 after:right-0 after:bottom-0 after:bg-slate-900/40 after:z-[1] rounded-lg"
				>
					<img src={offer.img} alt={offer.name} class="w-full aspect-video" />

					<div
						class="absolute top-0 left-0 h-full w-full py-3 px-6 [background-image:_url('/offer.svg')] bg-cover bg-bottom z-[2]"
					>
						<h3
							class="text-center text-xl lg:text-3xl text-primary-foreground absolute left-0 bottom-0 w-full h-[30%] inline-flex justify-center items-center"
						>
							{offer.name}
						</h3>
					</div>
				</div>
				<!-- </DialogTrigger> -->
			{/each}
		</div>

		<!-- <OfferDialog detail={offerDetails} /> -->
		<!-- </DialogRoot> -->
	</div>
</section>
