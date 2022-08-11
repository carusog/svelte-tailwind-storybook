<script>
	import { Meta, Story, Template } from '@storybook/addon-svelte-csf';
	// FIXME: the alias won't work,
	import Button from '$lib/components/Button.svelte';
	// import Button from './Button.svelte'; // <-- this is the working syntax

	let count = 0;

	function handleClick() {
		count += 1;
	}
</script>

<Meta title="Native Stories/Button" component={Button} />

<Template let:args>
	<Button {...args} on:click={handleClick}>
		You clicked: {count}
	</Button>
</Template>

<Story name="Native Story Button" />

<!-- Dynamic snippet should be disabled for this story -->
<!-- <Story name="Button No Args">
     <Button>Label</Button>
     </Story> -->
