<script lang="ts">
	import { createEventDispatcher } from 'svelte';
	export let text = '';
	const dispatch = createEventDispatcher();

	function onClick(event: MouseEvent): void {
		dispatch('click', event);
	}
</script>

<button class="button" on:click={onClick}>
	{text}
	<slot />
</button>

<style lang="postcss">
	.button {
		@apply ease-in duration-300 rounded-full px-4 py-2 text-white bg-cyan-700 border-4 border-cyan-600 hover:outline outline-4 outline-cyan-500;
	}
</style>
