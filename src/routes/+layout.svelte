<script lang="ts">
	import '../app.css';

	import Navlink from './Navlink.svelte';
	import Icon from '@iconify/svelte';
</script>

<nav class="py-4 px-16 flex gap-4 justify-center bg-neutral-600 items-center">
	<Navlink><Icon icon="mdi-light:home" height="2em" /></Navlink>
	<Navlink href="/about">About</Navlink>
	<Navlink>Portfolio</Navlink>
	<Navlink>Contact</Navlink>
	<Navlink>Blog</Navlink>
</nav>

<slot />
