<script>
	// @ts-nocheck

	import { fly, fade } from 'svelte/transition';
	import { page } from '$app/stores';

	import { onMount } from 'svelte';

	import Button from '../components/Button.svelte';

	let ready = false;
	onMount(() => (ready = true));
</script>

{#if ready}
	<div class="flex flex-col text-center items-center gap-5">
		<div>
			<h1 in:fly={{ duration: 850, y: 100 }}>{$page.status}</h1>
			<h1 in:fly={{ duration: 850, delay: 300, y: 80 }}>{$page.error.message}</h1>
		</div>
		{#if $page.status == 404}
			<h3>
				{#each 'OwO what are you searching for? :p' as char, i}
					<span in:fade={{ delay: 1000 + i * 80, duration: 400 }}>{char}</span>
				{/each}
			</h3>
		{/if}
		{#if $page.status == 500}
			<h3>
				{#each "It's feature trust me" as char, i}
					<span in:fade={{ delay: 2000 + i * 120, duration: 800 }}>{char}</span>
				{/each}
			</h3>
		{/if}

		<div in:fly={{ duration: 3500, y: 80, delay: 3400 }}>
			<Button text="Home" link="/" delay={3450} />
		</div>
	</div>
{/if}
