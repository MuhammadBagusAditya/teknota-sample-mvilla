<script lang="ts">
	import { cn } from '$lib/utils';

	let isLoading = $state(true);

	$effect(() => {
		window.addEventListener('load', () => {
			isLoading = false;
		});
	});
</script>

<div
	class={cn(
		'fixed top-0 left-0 right-0 bottom-0 bg-white flex-col gap-3 justify-center items-center z-[100]',
		isLoading ? 'flex' : 'hidden'
	)}
>
	<div class="flex gap-4 items-center h-[4rem]">
		<span
			class="bg-primary w-[0.75rem] h-[0.75rem] rounded-full animate-loading [animation-delay:_0]"
		></span>
		<span
			class="bg-primary w-[0.75rem] h-[0.75rem] rounded-full animate-loading [animation-delay:_200ms]"
		></span>
		<span
			class="bg-primary w-[0.75rem] h-[0.75rem] rounded-full animate-loading [animation-delay:_400ms]"
		></span>
		<span
			class="bg-primary w-[0.75rem] h-[0.75rem] rounded-full animate-loading [animation-delay:_600ms]"
		></span>
	</div>

	<span class="text-xl">Mohon tunggu...</span>
</div>
