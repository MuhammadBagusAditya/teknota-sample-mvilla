<script lang="ts">
	import { Separator } from '$lib/components/ui/separator';
	import Icon from '@iconify/svelte';
	import { contacts } from '$lib/data.json';
</script>

<section id="contacts">
	<div class="container py-8">
		<h2 class="text-2xl md:text-3xl font-bold mb-8 text-slate-800 text-center">Hubungi Kami</h2>

		<div class="grid gap-3 lg:grid-cols-[400px,_1fr]">
			<div class="flex flex-col gap-3">
				<div class="grid sm:grid-cols-2">
					<a
						href={contacts.whatsapp}
						target="_blank"
						class="flex flex-col items-center gap-2 text-emerald-700"
					>
						<Icon icon="mdi:whatsapp" class="text-6xl" />
						Pesan via Whatsapp
					</a>

					<a
						href={contacts.youtube}
						target="_blank"
						class="flex flex-col items-center gap-2 text-red-700"
					>
						<Icon icon="mdi:youtube" class="text-6xl" />
						Cek Channel Youtube
					</a>
				</div>

				<Separator class="my-3" />

				<h5 class="inline-flex items-center gap-2 font-semibold text-slate-800">
					<Icon icon="mdi:map-marker" class="text-2xl" />
					Alamat
				</h5>

				<p>{contacts.location}</p>
			</div>

			<div>
				<!-- coord=-6.5917217984720144, 110.65430613776233&amp;q=Jl. A.E. Suryani No.63&amp;ie=UTF8&amp;t=&amp;z=14&amp;iwloc=B&amp; -->
				<iframe
					width="100%"
					height="300"
					src="https://maps.google.com/maps?width=100%&amp;height=600&amp;hl=en&amp;output=embed"
					frameborder="0"
					scrolling="no"
					marginheight="0"
					marginwidth="0"
					title="alamat usaha"
				></iframe>
			</div>
		</div>
	</div>
</section>
