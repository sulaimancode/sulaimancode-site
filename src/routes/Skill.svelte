<script lang="ts">
	export let name: string;
	let text1: SVGTextElement | undefined;

	let textWidth: number | undefined;
	let duration: number | undefined;

	$: if (text1) {
		textWidth = text1.getComputedTextLength();
		duration = textWidth / 200;
	}
</script>

<svg width="100%" height="100%" viewBox="0 0 800 200">
	<defs>
		<pattern id={`pattern-${name}`} patternUnits="userSpaceOnUse" width="800" height="200">
			{#if textWidth && duration}
				<rect x="0" y="0" height="200" width="0" fill="#ff4136">
					<animate
						attributeName="width"
						from="0"
						to={textWidth}
						dur={`${duration}s`}
						fill="freeze"
					/>

					<animate
						attributeName="fill"
						values="#ff4136; #ff851b; #2ecc40"
						keyTimes={`0; 0.6; 1`}
						dur={`${duration}s`}
						fill="freeze"
					/>
				</rect>
			{/if}
		</pattern>
	</defs>
	<text
		bind:this={text1}
		x="0"
		y="150"
		font-family="sans-serif"
		font-size="120"
		font-weight="900"
		style="stroke: white; stroke-width: 1px;">{name}</text
	>
	<text
		x="0"
		y="150"
		font-family="sans-serif"
		font-size="120"
		font-weight="900"
		fill={`url(#pattern-${name})`}
		style="stroke: white; stroke-width: 1px;">{name}</text
	>
</svg>
