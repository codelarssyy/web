<script lang="ts">
	import { fade } from 'svelte/transition';

	export let text: string;
	export let link: string;
    export let delay: number;
</script>

<a class="flex justify-center items-center text-xl border-2 rounded-xl bg-transparent text-white w-32 h-14" href={link}>
	{#each text as char, i}
		<span in:fade={{ delay: delay + i * 120, duration: 800 }}>{char}</span>
	{/each}
</a>
