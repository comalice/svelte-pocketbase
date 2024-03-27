<script>
	import UserActions from '$lib/UserActions.svelte';
	import { currentUser } from '$lib/pocketbase';
	import { Label, Input, Button, CloseButton } from 'flowbite-svelte';
	import { EnvelopeSolid } from 'flowbite-svelte-icons';
</script>

<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>

<UserActions />

<Label class="space-y-2">
	<span>Small input - left icon</span>
	<Input type="email" placeholder="name@flowbite.com" size="md">
		<EnvelopeSolid slot="left" class="w-4 h-4" />
	</Input>
</Label>
