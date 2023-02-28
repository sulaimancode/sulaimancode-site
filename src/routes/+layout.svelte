<script lang="ts">
	import '../app.css';

	import Navlink from './Navlink.svelte';
</script>

<div class="flex flex-col items-center mx-6">
	<nav
		class="flex justify-center items-center w-full gap-4 py-4 px-16 backdrop-blur-sm sticky top-0"
	>
		<Navlink>Home</Navlink>
		<Navlink>Skills</Navlink>
		<Navlink>Experience</Navlink>
		<Navlink>Contact</Navlink>
	</nav>
	<slot />
</div>
