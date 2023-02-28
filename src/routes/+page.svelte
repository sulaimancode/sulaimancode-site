<script>
	import Navlink from './Navlink.svelte';
</script>

<div class="flex flex-col items-center h-full">
	<nav
		class="flex justify-center items-center w-full gap-4 py-4 px-16 backdrop-blur-sm sticky top-0"
	>
		<Navlink>Home</Navlink>
		<Navlink>Skills</Navlink>
		<Navlink>Experience</Navlink>
		<Navlink>Contact</Navlink>
	</nav>

	<div class="flex flex-col gap-6 items-center justify-center my-auto sm:flex-row">
		<img
			src="/sulai-pic-sm.jpg"
			alt="Sulai's profile"
			class="rounded-full w-32 h-32 object-cover"
		/>
		<div class="bg-neutral-800 p-4 rounded-md w-[85%] sm:w-[60%]">
			<p>
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
