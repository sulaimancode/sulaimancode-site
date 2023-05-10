<script lang="ts">
	import Navlink from '../components/Navlink.svelte';
	import Skill from '../components/Skill.svelte';

	let animate = false;
	let skillsElement: HTMLElement | undefined;
	let intersectionObserver: IntersectionObserver | undefined;

	if (typeof IntersectionObserver !== 'undefined') {
		intersectionObserver = new IntersectionObserver(
			(entries) => {
				entries.forEach((entry) => {
					if (entry.isIntersecting) {
						animate = true;
					}
				});
			},
			{ threshold: 0.5 }
		);
	}

	$: if (skillsElement && intersectionObserver) {
		intersectionObserver.observe(skillsElement);
	}
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

	<article class="mb-16">
		<h2 class="mb-2 text-xl font-bold">About me</h2>
		<p class="mb-4 text-slate-300">
			I am a software engineer with 4+ years of professional experience. I have a deep passion for
			building and creating with code. I first began teaching myself to code using online resources,
			but I soon realized I needed a more immersive learning experience. That's when I discovered <a
				class="text-blue-300 hover:underline"
				href="https://www.makers.tech/">Makers</a
			>, an intensive coding bootcamp where I had the opportunity to learn alongside an incredible
			group of peers.
		</p>
		<p class="mb-4 text-slate-300">
			Since then, I've worked across the stack, but I have a particular affinity for frontend
			technology. I've honed my skills in Typescript, React and Redux, and I'm always eager to learn
			more about the latest tools and techniques in the field.
		</p>
		<p class="text-slate-300">
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

	<div bind:this={skillsElement} class="mb-16">
		<h2 class="mb-2 text-xl font-bold">Skills</h2>
		<ul class="flex list-none flex-wrap gap-4">
			<Skill name="HTML" level={0.97} {animate} />
			<Skill name="CSS" level={0.59} {animate} />
			<Skill name="Typescript" level={0.79} {animate} />
			<Skill name="React" level={0.9} {animate} />
			<Skill name="Redux" level={0.7} {animate} />
			<Skill name="SvelteKit" level={0.25} {animate} />
			<Skill name="C#" level={0.2} {animate} />
			<Skill name="Ruby" level={0.2} {animate} />
		</ul>
	</div>

	<section>
		<h2 class="mb-2 text-xl font-bold">Experience</h2>

		<ol class="relative border-l border-gray-200 dark:border-gray-700">
			<li class="mb-10 ml-4">
				<div
					class="absolute -left-1.5 mt-1.5 h-3 w-3 rounded-full border border-white bg-gray-200 dark:border-gray-900 dark:bg-gray-700"
				/>
				<time class="mb-1 text-sm font-normal leading-none text-gray-400 dark:text-gray-500"
					>Jun 2022 - present</time
				>
				<h3 class="text-lg font-semibold text-gray-900 dark:text-white">Ocado Technology</h3>
				<p class="mb-4 text-base font-normal text-gray-500 dark:text-slate-300">
					Building robust and accessible UI for the Ocado smart platform
				</p>
			</li>
			<li class="mb-10 ml-4">
				<div
					class="absolute -left-1.5 mt-1.5 h-3 w-3 rounded-full border border-white bg-gray-200 dark:border-gray-900 dark:bg-gray-700"
				/>
				<time class="mb-1 text-sm font-normal leading-none text-gray-400 dark:text-gray-500"
					>Nov 2017 - Dec 2020</time
				>
				<h3 class="text-lg font-semibold text-gray-900 dark:text-slate-300">Redgate Software</h3>
				<p class="text-base font-normal text-gray-500 dark:text-slate-300">
					Worked on several desktop applications using Electron and .Net
				</p>
			</li>
		</ol>
	</section>
</div>
