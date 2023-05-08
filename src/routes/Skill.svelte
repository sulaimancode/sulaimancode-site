<script lang="ts">
	export let name: string;
	export let level: number;

	const red = '#ff4136';
	const orange = '#ff851b';
	const green = '#2ecc40';

	let animateValues = `${red}; ${red}; ${orange}; ${orange}; ${green}`;
	let animateKeyTimes = '0; 0.4; 0.5; 0.55; 1';

	if (level < 0.6) {
		animateValues = `${red}; ${red}; ${orange}; ${orange}`;
		animateKeyTimes = '0; 0.4; 0.5; 1';
	}

	if (level < 0.3) {
		animateValues = `${red}; ${red}`;
		animateKeyTimes = '0; 1';
	}

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
						to={textWidth * level}
						dur={`${duration}s`}
						fill="freeze"
					/>

					<animate
						attributeName="fill"
						values={animateValues}
						keyTimes={animateKeyTimes}
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
		class="stroke-white stroke-1">{name}</text
	>
	<text
		x="0"
		y="150"
		font-family="sans-serif"
		font-size="120"
		font-weight="900"
		fill={`url(#pattern-${name})`}
		class="stroke-white stroke-1">{name}</text
	>
</svg>
