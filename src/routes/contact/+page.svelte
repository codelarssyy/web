<script>
	import { fade, fly } from 'svelte/transition';
	import { onMount } from 'svelte';
	import Button from '../../components/Button.svelte';

	let ready = false;
	onMount(() => (ready = true));
</script>

{#if ready}
	<div class="relative flex flex-col xl:items-start items-center xl:px-40 pb-4">
		<h1 in:fly={{ duration: 850, y: 80 }}>Contact</h1>
		<h2 in:fly={{ delay: 200, duration: 850, y: 80 }}>
			You can contact me at <a
				class="border-[#fff3] hover:border-[#fff9] border-b-2"
				href="mailto:contact@larsylab.org"
			>
				contact@larsylab.org
			</a>
		</h2>
		<h3 in:fly={{ delay: 1200, duration: 850, y: 80 }}>Or the easier way...</h3>
		<div class="text-3xl">
			<a href="https://discord.com/users/1089191436475449455">
				<i
					class="fa-brands fa-discord text-[#5865f2]"
					in:fly={{ delay: 1600, duration: 850, x: 100 }}
				/>
			</a>
		</div>
        <div class="mt-5" in:fly={{ duration: 850, y: 80, delay: 2000 }}>

            <Button text="Return" link="/" delay={2200}/>
        </div>
	</div>
{/if}
