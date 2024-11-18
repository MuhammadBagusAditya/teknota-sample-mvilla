<script module>
	import * as Card from '$lib/components/ui/card';
	import * as Carousel from '$lib/components/ui/carousel';
	import { Button } from '$lib/components/ui/button';
	import Autoplay from 'embla-carousel-autoplay';
	import Fade from 'embla-carousel-fade';
	import Icon from '@iconify/svelte';
	import { villas } from '$lib/data.json';
	import { priceFormatter } from '$lib/helpers/formatter';
</script>

<section id="villas">
	<div class="container py-8">
		<!-- <h2 class="text-center font-bold text-slate-800 text-3xl mb-8">Villa Kami</h2> -->

		<div class="flex flex-col gap-8">
			{#each villas as villa}
				<Card.Root class="w-full shadow shadow-slate-900/20">
					<Card.Content
						class="grid grid-rows-[repeat(2,_auto)] md:grid-rows-1 grid-cols-1 md:grid-cols-[20rem,_1fr] xl:grid-cols-[35rem,_1fr] gap-8"
					>
						<Carousel.Root
							plugins={[Autoplay({ stopOnInteraction: false }), Fade()]}
							opts={{ loop: true }}
							class="flex"
						>
							<Carousel.Content class="h-full">
								{#each villa.images as image}
									<Carousel.Item class="h-full aspect-square md:aspect-auto">
										<img
											src={image.url}
											alt={image.alt}
											class="rounded-lg h-full w-full object-cover object-center"
										/>
									</Carousel.Item>
								{/each}
							</Carousel.Content>
						</Carousel.Root>

						<div class="h-full flex flex-col">
							<div class="flex justify-between items-center gap-4 mb-4">
								<Card.Title class="text-2xl md:text-3xl lg:text-4xl text-slate-800">
									{villa.name}
								</Card.Title>

								<span class="text-slate-700">{priceFormatter.format(villa.price)}</span>
							</div>

							<ul class="list-disc text-slate-700 pl-4 space-y-3 mb-8 flex-1">
								{#each villa.facilities as facility}
									<li>{facility}</li>
								{/each}
							</ul>

							<div class="flex justify-center md:justify-end items-center gap-3">
								<Button class="rounded-full">
									Pesan Sekarang
									<Icon icon="mdi:arrow-right" class="text-xl ml-2" />
								</Button>
							</div>
						</div>
					</Card.Content>
				</Card.Root>
			{/each}
		</div>
	</div>
</section>
