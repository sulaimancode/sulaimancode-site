<script lang="ts">
	export let date: string;
	export let company: string;
	export let description: string;
</script>

<li class="mb-10 ml-4">
	<div
		class="absolute -left-1.5 mt-1.5 h-3 w-3 rounded-full border border-white bg-gray-200 dark:border-gray-900 dark:bg-gray-700"
	/>
	<time class="mb-1 text-sm font-normal leading-none text-gray-500">{date}</time>
	<h3 class="text-lg font-semibold">{company}</h3>
	<p class="mb-4 text-base font-normal text-slate-300">{description}</p>
</li>
