<script lang="ts">
	import { goto } from '$app/navigation';
	import { currentUser, errorMessage, pocketbase } from '$lib/pocketbase';

	async function handleSignOut() {
		try {
			pocketbase.authStore.clear();
		} catch (error) {
			errorMessage(error);
		}
	}
</script>


{#if !$currentUser}
<div class="flex flex-col items-center justify-center w-full py-20">
    <button
		class="group relative flex w-1/2 justify-center rounded-md border border-transparent bg-indigo-600 py-2 px-4 text-sm font-medium text-white hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2 mt-2"
        on:click={() => {goto("/Login")}}
        >Login</button>
</div>
{:else}
<div class="flex flex-col items-center justify-center w-full py-20">
	<p>{$currentUser.email}</p>
	<button
		class="group relative flex w-1/2 justify-center rounded-md border border-transparent bg-indigo-600 py-2 px-4 text-sm font-medium text-white hover:bg-indigo-700 focus:outline-none focus:ring-2 focus:ring-indigo-500 focus:ring-offset-2 mt-2"
		on:click={handleSignOut}
	>
		<span class="absolute inset-y-0 left-0 flex items-center pl-3" />
		Sign Out
	</button>
</div>
{/if}