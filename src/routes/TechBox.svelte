<script lang="ts">
	export let top: string;
	export let color: string;
	let clicked = false;

	const colorVariants: Record<string, string> = {
		red: 'bg-red-600',
		blue: 'bg-blue-600',
		green: 'bg-green-600',
		yellow: 'bg-yellow-600',
		purple: 'bg-purple-600',
		pink: 'bg-pink-600',
		gray: 'bg-gray-600',
		indigo: 'bg-indigo-600',
		orange: 'bg-orange-600',
		teal: 'bg-teal-600'
	};

	const handleClick = () => {
		console.log('clicked');
		clicked = !clicked;
	};
</script>

<div
	class="{clicked && 'animate-[slide_1s_ease-in-out_forwards]'} {colorVariants[
		color
	]} w-32 h-32 absolute {top}"
	on:click={handleClick}
	on:keydown={handleClick}
/>
