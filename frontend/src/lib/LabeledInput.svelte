<script>
	import { Label, Input } from 'flowbite-svelte';

	export let label = '';
	export let id = '';
	export let type = 'text';
	export let value = '';
	export let placeholder = '';
	export let helperText = '';
    export let required = false;
</script>

<div class="mb-2">
	<Label for={id}>{label}</Label>
	<Input {id} {type} bind:value {placeholder}/>
	{#if helperText}
		<div class="text-sm text-gray-500">{helperText}</div>
	{/if}
</div>
