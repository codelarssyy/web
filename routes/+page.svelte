<script>
	import { fade, fly } from 'svelte/transition';
	import { onMount } from 'svelte';
	import Button from '../components/Button.svelte';

	let ready = false;
	onMount(() => (ready = true));
</script>

<svelte:head>
	<title>Larsy | Home</title>
	<meta name="description" content="Just my personal page" />
</svelte:head>

{#if ready}
	<div
		class="flex flex-col xl:flex-row justify-between items-center xl:text-start text-center overflow-hidden md:px-40 md:pb-20"
	>
		<div>
			<h1 in:fly={{ duration: 850, y: 80 }}>Hi there 👋</h1>
			<h2 in:fly={{ delay: 1000, duration: 850, y: 100 }}>
				Im {#each 'Larsy 👀' as char, i}
					<span in:fade={{ delay: 2000 + i * 120, duration: 800 }}>{char}</span>
				{/each}
			</h2>

			<h3 in:fly={{ delay: 3000, duration: 850, y: 80 }}>Self-Taught Software engineer</h3>
			<h3 in:fly={{ delay: 3700, duration: 850, y: 80 }}>Web designer</h3>
			<!-- <h3 in:fly={{ delay: 4300, duration: 850, y: 80 }}>sharify.in Founder</h3> -->
			<h3 in:fly={{ delay: 4700, duration: 850, y: 80 }}>aaand... idk...</h3>
			<!-- 			<h3 in:fly={{ delay: 3900, duration: 850, y: 80 }}>
            And proud founder of {#each 'Nothing...' as char, i}
                <span in:fade={{ delay: 4400 + i * 120, duration: 800 }}>{char}</span>
            {/each}
        </h3> -->

			<div class="relative flex gap-5 text-3xl xl:justify-start justify-center mt-5">
				<a href="https://github.com/codelarssyy" in:fly={{ delay: 5400, duration: 850, x: 100 }}>
					<i class="fa-brands fa-github" />
				</a>
				<a href="https://discord.com/users/1089191436475449455" in:fly={{ delay: 5600, duration: 850, x: 100 }}>
					<i id="discord-icon" class="fa-brands fa-discord text-[#5865f2]" /></a
				>
				<a
					id="guilded-icon"
					href="https://www.guilded.gg/u/codelarsy"
					in:fly={{ delay: 5800, duration: 850, x: 100 }}
				>
					<i class="fa-brands fa-guilded text-[#f5c400]" />
				</a>
				<!-- <a
					href="https://steamcommunity.com/id//"
					in:fly={{ delay: 6000, duration: 850, x: 100 }}
				>
					<i class="fa-brands fa-steam" />
				</a>
				-->
			</div>
		</div>
		<div class="relative flex md:flex-row flex-col justify-center gap-5 md:mt-0 mt-5">
			<div in:fly={{ duration: 850, x: 100 }}>
				<Button text="Projects" link="/projects" delay={100} />
			</div>
			<div in:fly={{ duration: 850, x: 100, delay: 400 }}>
				<Button text="Contact" link="/contact" delay={250} />
			</div>
		</div>
	</div>
{/if}
