<script lang="ts">
	import { DialogContent, Title } from '$lib/components/ui/dialog';

	let { detail }: { detail: OfferDetail } = $props();
</script>

<DialogContent class="">
	<Title>{detail.name}</Title>

	<div class="w-full h-[40dvh]">
		<img src={detail.img} alt={detail.name} class="w-full object-contain object-center" />
	</div>
</DialogContent>
