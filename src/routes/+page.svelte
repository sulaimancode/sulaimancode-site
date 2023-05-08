<script lang="ts">
	import Navlink from './Navlink.svelte';
	import ListItem from './ListItem.svelte';
	import Skill from './Skill.svelte';

	let animate = false;
</script>

<nav class="sticky top-0 flex w-full items-center justify-center gap-4 py-4 px-16 backdrop-blur-sm">
	<Navlink>Home</Navlink>
	<Navlink>Skills</Navlink>
	<Navlink>Experience</Navlink>
	<Navlink>Contact</Navlink>
</nav>

<div class="mx-auto w-[60%]">
	<div class="py-40">
		<h1 class="text-center text-3xl font-bold">
			Hello <span class="inline-block origin-[70%_70%] animate-wave-animation">👋</span>
			I am Sulaiman, a software engineer based in the UK.
		</h1>
	</div>

	<article class="mb-4">
		<h2 class="mb-2 text-xl font-bold">About me</h2>
		<p class="mb-4">
			I am a software engineer with 4+ years of professional experience. I have a deep passion for
			building and creating with code. I first began teaching myself to code using online resources,
			but I soon realized I needed a more immersive learning experience. That's when I discovered <a
				class="text-blue-200 hover:underline"
				href="https://www.makers.tech/">Makers</a
			>, an intensive coding bootcamp where I had the opportunity to learn alongside an incredible
			group of peers.
		</p>
		<p class="mb-4">
			Since then, I've worked across the stack, but I have a particular affinity for frontend
			technology. I've honed my skills in Typescript, Javascript, React, Redux, and
			React-testing-library, and I'm always eager to learn more about the latest tools and
			techniques in the field.
		</p>
		<p>
			Currently I'm working at
			<a
				class="text-blue-200 hover:underline"
				href="https://www.ocadogroup.com/about-us/ocado-technology/">Ocado Technology</a
			>, building robust and accessible UIs for the
			<a
				class="text-blue-200 hover:underline"
				href="https://www.ocadogroup.com/about-us/what-we-do/ocado-smart-platform/"
				>Ocado Smart Platform</a
			>
		</p>
	</article>

	<article>
		<h2 class="mb-2 text-xl font-bold">Skills</h2>
		<div class="flex flex-wrap gap-4">
			<Skill name="Typescript" level={0.9} {animate} />
			<Skill name="React" level={0.8} {animate} />
			<Skill name="Redux" level={0.7} {animate} />
			<Skill name="SvelteKit" level={0.25} {animate} />
			<Skill name="Ruby" level={0.5} {animate} />
		</div>
		<button
			on:click={() => {
				animate = true;
			}}>click to animate</button
		>
		<h1>Other stuff I've used:</h1>
		<ul>
			<ListItem>C#</ListItem>
			<ListItem>.Net</ListItem>
			<ListItem>Ruby</ListItem>
		</ul>
	</article>
</div>
