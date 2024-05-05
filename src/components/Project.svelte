<script lang="ts">
	export let title: string;
	export let description: string;
	export let link: string;
</script>

<div class="flex flex-col gap-3 border-2 rounded-xl backdrop-blur md:w-80 w-full mt-3 p-5">
	<div>
		<a class="text-2xl border-[#fff3] hover:border-[#fff9] border-b-2" href={link}>{title}</a>
	</div>
	<p>{description}</p>
</div>
