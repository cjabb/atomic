<script lang="ts">
	import { onMount } from 'svelte';
	import { fade } from 'svelte/transition';
	import Logo from '$lib/components/Logo.svelte';
	import Navbar from '$lib/components/Navbar.svelte';
	import TeamMember from '$lib/components/TeamMember.svelte';
	import ProjectCard from '$lib/components/ProjectCard.svelte';
	import SkillsCard from '$lib/components/SkillsCard.svelte';
	import { goto } from '$app/navigation';

	const teamMembers = [
		{
			name: 'Charbel',
			role: 'Full-stack Developer',
			image: 'charbel.jpg',
			github: 'https://github.com/lunartaku',
			linkedin: '#',
			email: 'charbel81jabbour@gmail.com',
			skills: ['JavaScript', 'HTML', 'CSS', 'Node.js', 'Bun.sh', 'SvelteKit']
		},
		{
			name: 'Roland',
			role: 'Full-stack Developer',
			image:
				'https://cdn.discordapp.com/avatars/856934780015607858/e13b5867155946a4803665b71f236825.webp?size=1024&format=webp&width=0&height=256',
			github: 'https://github.com/rolxndxd',
			linkedin: 'https://www.linkedin.com/in/roland-chalhoub-5aa502244?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=android_app',
			email: 'rolandchalhoub134@gmail.com',
			skills: ['JavaScript', 'HTML', 'CSS', 'Python', 'Java']
		}
	];

	const projects = [
		{
			name: 'Space',
			description: 'A open source image board, with authentication, image uploading, and more.',
			technologies: ['SvelteKit', 'Node.sh', 'TailwindCSS', 'TypeScript'],
			link: 'https://github.com/LunarTaku/space'
		},
		{
			name: 'Electron',
			description:
				'A music bot designed to stream music from multiple sources including Spotify, radio, and others!',
			technologies: ['JavaScript', 'Discord.js', 'Node.js'],
			link: 'https://atomicdev.org/electron/index.html'
		},
		{
			name: 'Pfps',
			description:
				"pfps.site is a website we created and devolved. It's purpose is to let people post a picture through the website or through discord, their picture would be listed in a category of their choice with other pfps published by others!",
			technologies: ['Node.js', 'Express', 'MongoDB'],
			link: ''
		}
	];

	const skills = [
		'JavaScript',
		'HTML',
		'CSS',
		'Node.js',
		'Bun.sh',
		'SvelteKit',
		'Python',
		'Java',
		'MongoDB',
		'Express',
		'D3.js',
		'Git'
	];

	let mounted = false;

	onMount(() => {
		mounted = true;
	});

	function redirectTo(link: string) {
		window.location.href = link;
	}
</script>

<svelte:head>
	<title>Atomic Development</title>
	<link
		href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&display=swap"
		rel="stylesheet"
	/>
  
</svelte:head>

<div class="font-poppins min-h-screen bg-gray-900 text-gray-100">
	<Navbar />

	<main class="container mx-auto px-4 py-12">
		<section id="hero" class="mb-16 text-center">
			<h1 class="mb-6 text-5xl font-bold">Atomic Development</h1>
			<p class="mb-8 text-xl text-gray-300">
				We build cutting-edge web solutions with atomic precision.
			</p>
			<a
				href="#projects"
				class="rounded-full bg-blue-600 px-8 py-3 text-lg font-semibold text-white transition-all duration-300 hover:bg-blue-700"
			>
				View Our Projects
			</a>
		</section>

		<section id="team" class="mb-16">
			<h2 class="mb-6 text-3xl font-semibold">Our Team</h2>
			<div class="grid grid-cols-1 gap-8 md:grid-cols-2">
				{#each teamMembers as member}
					<TeamMember {member} />
				{/each}
			</div>
		</section>

		<section id="projects" class="mb-16">
			<h2 class="mb-6 text-3xl font-semibold">Our Projects</h2>
			<div class="grid grid-cols-1 gap-6 md:grid-cols-2 lg:grid-cols-3">
				{#each projects as project}
					<ProjectCard {project} on:click={() => redirectTo(project.link)} />
				{/each}
			</div>
		</section>

		<section id="skills">
			<h2 class="mb-6 text-3xl font-semibold">Our Collective Skills</h2>
			<SkillsCard {skills} />
		</section>
	</main>

	<footer class="mt-12 bg-gray-800 p-6">
		<div class="container mx-auto text-center">
			<p>&copy; 2023 Atomic Development. All rights reserved.</p>
		</div>
	</footer>
</div>

<style>
	:global(body) {
		font-family: 'Poppins', sans-serif;
	}

	:global(.hover-illuminate) {
		position: relative;
		overflow: hidden;
	}

	:global(.hover-illuminate::before) {
		content: '';
		position: absolute;
		top: -100%;
		left: -100%;
		width: 300%;
		height: 300%;
		background: radial-gradient(circle, rgba(255, 255, 255, 0.2) 0%, transparent 70%);
		transition: all 0.3s ease;
		opacity: 0;
		pointer-events: none;
	}

	:global(.hover-illuminate:hover::before) {
		opacity: 1;
	}
</style>
