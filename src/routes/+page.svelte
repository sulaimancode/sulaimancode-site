<script lang="ts">
	import Link from '../components/Link.svelte';
	import Skill from '../components/Skill.svelte';
	import TimelineItem from '../components/TimelineItem.svelte';
	import Icon from '@iconify/svelte';

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
			{ threshold: 0.8 }
		);
	}

	$: if (skillsElement && intersectionObserver) {
		intersectionObserver.observe(skillsElement);
	}
</script>

<svelte:head>
	<title>Sulaiman Ahmadshah - Homepage</title>
</svelte:head>

<main class="mx-auto max-w-2xl px-3">
	<div class="py-60">
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
		<p class="mb-4 text-slate-300">
			Currently I'm working at
			<Link href="https://www.ocadogroup.com/about-us/ocado-technology/">Ocado Technology</Link>,
			building robust and accessible UIs for the
			<Link href="https://www.ocadogroup.com/about-us/what-we-do/ocado-smart-platform/"
				>Ocado Smart Platform</Link
			>.
		</p>
		<div class="flex gap-4 text-slate-300">
			<a href="https://github.com/sulaimancode" class="hover:text-white"
				><Icon icon="bi:github" width="2rem" height="2rem" />
				<span class="sr-only">Sulaiman's Github</span>
			</a>
			<a href="https://www.linkedin.com/in/slaiman-ahmadshah-057251147/" class="hover:text-white"
				><Icon icon="bi:linkedin" width="2rem" height="2rem" />
				<span class="sr-only">Sulaiman's LinkedIn</span>
			</a>
		</div>
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

	<section class="mb-16">
		<h2 class="mb-2 text-xl font-bold">Experience</h2>

		<ol class="relative border-l border-gray-200 dark:border-gray-700">
			<TimelineItem
				date="2022 - Present"
				company="Ocado Technology"
				description="Building robust and accessible UIs for the Ocado smart platform"
			/>
			<TimelineItem
				date="2017 - 2020"
				company="Redgate Software"
				description="Worked on several desktop applications using Electron and .Net"
			/>
		</ol>
	</section>

	<section class="mb-16">
		<h2 class="mb-2 text-xl font-bold">Contact</h2>
		<p class="text-slate-300">
			Feel free to reach out to me with anything interesting <a
				href="mailto:sulaimanahmad321@gmail.com"
				class="font-bold">sulaimanahmad321@gmail.com</a
			>
		</p>
	</section>
</main>

<footer class="mb-8">
	<hr class="my-6 border-gray-700 sm:mx-auto" />
	<div class="flex items-center gap-1 sm:justify-center">
		<span class="text-sm text-gray-400"
			>Created with <Link href="https://tailwindcss.com/">TailwindCSS</Link> and <Link
				href="https://kit.svelte.dev/">SvelteKit</Link
			>.
		</span>
		<a
			href="https://github.com/sulaimancode/sulaimancode-site"
			class="flex items-center gap-1 text-sm text-gray-400 hover:cursor-pointer hover:text-white"
		>
			<Icon icon="bi:github" /> Source
		</a>
	</div>
</footer>
