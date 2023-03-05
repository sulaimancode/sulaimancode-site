<script>
	import Navlink from './Navlink.svelte';
	import ListItem from './ListItem.svelte';
</script>

<div class="flex flex-col items-center gap-16">
	<nav
		class="sticky top-0 flex w-full items-center justify-center gap-4 py-4 px-16 backdrop-blur-sm"
	>
		<Navlink>Home</Navlink>
		<Navlink>Skills</Navlink>
		<Navlink>Experience</Navlink>
		<Navlink>Contact</Navlink>
	</nav>

	<p>Hello 👋 I am Sulaiman, a software engineer based in the UK.</p>

	<div class="p-6 grid grid-cols-2 gap-44">
		<div>
			<h1 class="text-xl ">About me</h1>
			<p class="mb-4">
				I am a software engineer with 4+ years of professional experience. I have a deep passion for
				building and creating with code. I first began teaching myself to code using online
				resources, but I soon realized I needed a more immersive learning experience. That's when I
				discovered <a class="text-blue-200 hover:underline" href="https://www.makers.tech/"
					>Makers</a
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
		</div>

		<div class="flex flex-col gap-4">
			<h1>Tech I am currently using:</h1>
			<ul>
				<ListItem>Javascript</ListItem>
				<ListItem>Typescript</ListItem>
				<ListItem>React</ListItem>
				<ListItem>Redux</ListItem>
				<ListItem>SvelteKit (using it to build this website, don't ask me why)</ListItem>
			</ul>
			<h1>Other stuff I've used:</h1>
			<ul>
				<ListItem>C#</ListItem>
				<ListItem>.Net</ListItem>
				<ListItem>Ruby</ListItem>
			</ul>
		</div>
	</div>
</div>
