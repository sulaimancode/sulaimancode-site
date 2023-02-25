<script lang="ts">
	import '../app.css';

	import Navlink from './Navlink.svelte';
</script>

<nav class="py-4 px-16 flex gap-4 justify-center bg-neutral-600 items-center">
	<Navlink>Contact</Navlink>
</nav>

<slot />
