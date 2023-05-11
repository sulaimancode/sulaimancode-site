<script lang="ts">
	import Link from '../components/Link.svelte';
	import Navlink from '../components/Navlink.svelte';
	import Skill from '../components/Skill.svelte';
	import TimelineItem from '../components/TimelineItem.svelte';

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

<div class="mx-auto max-w-2xl px-6">
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
			but I soon realized I needed a more immersive learning experience. That's when I discovered <Link
				href="https://www.makers.tech/">Makers</Link
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
			<Link href="https://www.ocadogroup.com/about-us/ocado-technology/">Ocado Technology</Link>,
			building robust and accessible UIs for the
			<Link href="https://www.ocadogroup.com/about-us/what-we-do/ocado-smart-platform/"
				>Ocado Smart Platform</Link
			>.
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
			<TimelineItem
				date="2021 - Present"
				company="Ocado Technology"
				description="Building robust and accessible UI for the Ocado smart platform"
			/>
			<TimelineItem
				date="2017 - 2020"
				company="Redgate Software"
				description="Worked on several desktop applications using Electron and .Net"
			/>
		</ol>
	</section>
</div>
