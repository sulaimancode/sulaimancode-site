<script lang="ts">
	import '../app.css';

	import Navlink from './Navlink.svelte';
</script>

<nav class="py-4 px-16 flex gap-4 justify-center bg-neutral-600">
	<Navlink href="/about">About</Navlink>
	<Navlink>Portfolio</Navlink>
	<Navlink>Contact</Navlink>
	<Navlink>Blog</Navlink>
</nav>

<slot />
