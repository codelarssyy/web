<script>
	import { fade, fly } from 'svelte/transition';
	import { onMount } from 'svelte';
	import Button from '../../components/Button.svelte';
	import Project from '../../components/Project.svelte';

	let ready = false;
	onMount(() => (ready = true));
</script>

{#if ready}
<div class="flex flex-col xl:items-start items-center xl:px-40 px-3 md:pb-20 pb-4">
	<h1 in:fly={{ duration: 850, y: 80 }}>Projects</h1>
	<div class="flex gap-5 flex-wrap" in:fly={{ duration: 850, y: 80, delay: 200 }}>
		<p>Making Automated System Stay Tuned...</p>
		</div>
	<div class="relative mt-5" in:fly={{ duration: 850, y: 80, delay: 300 }}>
		<Button text="Return" link="/" delay={150}/>
	</div>
</div>
{/if}
