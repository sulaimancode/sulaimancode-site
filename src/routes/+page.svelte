<script>
	import Navlink from './Navlink.svelte';
</script>

<div class="flex flex-col items-center mx-6 h-full">
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
		<h1 class="text-lg">Hello 👋, I am a passionate Software developer based in the the UK</h1>
	</div>
</div>
