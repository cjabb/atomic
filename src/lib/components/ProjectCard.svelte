<script lang="ts">
	import { goto } from '$app/navigation';

	export let project: {
		name: string;
		description: string;
		technologies: string[];
		link: string;
	};
</script>

<!-- svelte-ignore a11y-click-events-have-key-events -->
<!-- svelte-ignore a11y-no-static-element-interactions -->
<div
	class="hover-illuminate cursor-pointer rounded-lg bg-gray-800 p-6 shadow-lg"
	on:click
>
	<h3 class="mb-2 text-xl font-semibold">{project.name}</h3>
	<p class="mb-4 text-gray-400">{project.description}</p>
	<div class="flex flex-wrap gap-2">
		{#each project.technologies as tech}
			<span class="rounded-full bg-blue-600 px-2 py-1 text-sm text-white">
				{tech}
			</span>
		{/each}
	</div>
</div>
