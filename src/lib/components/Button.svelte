<script lang="ts">
	import { createEventDispatcher } from 'svelte';
	export let text = '';
	const dispatch = createEventDispatcher();

	function onClick(event: MouseEvent): void {
		// FIXME: unexpected token, because of the parameter's type and the return type
		// Isn't TypeScript supported?
		// function onClick(event) { // <-- this is the working syntax
		dispatch('click', event);
	}
</script>

<button class="button" on:click={onClick}>
	{text}
	<slot />
</button>

<style lang="postcss">
	.button {
		@apply rounded-full px-4 py-2 text-white bg-cyan-700 border-4 border-cyan-600;
	}
	.button:hover {
		@apply outline outline-4 outline-cyan-500;
	}
</style>
