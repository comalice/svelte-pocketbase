<script>
	import UserActions from "$lib/UserActions.svelte";
    import { currentUser } from "$lib/pocketbase";

</script>

<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>

<UserActions />