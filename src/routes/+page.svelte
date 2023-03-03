<script>
	import Navlink from './Navlink.svelte';
</script>

<div class="flex h-full flex-col items-center">
	<nav
		class="sticky top-0 flex w-full items-center justify-center gap-4 py-4 px-16 backdrop-blur-sm"
	>
		<Navlink>Home</Navlink>
		<Navlink>Skills</Navlink>
		<Navlink>Experience</Navlink>
		<Navlink>Contact</Navlink>
	</nav>

	<div class="my-auto flex flex-col items-center justify-center gap-6 sm:flex-row">
		<img
			src="/sulai-pic-sm.jpg"
			alt="Sulai's profile"
			class="h-32 w-32 rounded-full object-cover"
		/>
		<div class="w-[85%] rounded-md bg-neutral-800 p-4 sm:w-[60%]">
			<p  >
				Hello 👋 I am Sulaiman, a software engineer from the UK. I enjoy creating and building stuff
				with code. Currently working at <a
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
	</div>
</div>
