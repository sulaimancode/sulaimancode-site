<script lang="ts">
	export let name: string;
	export let level: number;
	export let animate: boolean;

	const red = '#ff4136';
	const orange = '#ff851b';
	const green = '#2ecc40';
	const fontSize = 30;

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

	let svg: SVGSVGElement | undefined;
	let text1: SVGTextElement | undefined;

	let textWidth: number | undefined;
	let duration: number | undefined;
	let svgWidth: number = 0;

	$: if (svg && text1) {
		textWidth = text1.getComputedTextLength();
		duration = textWidth / 100;

		const bbox = svg.getBBox();
		svgWidth = bbox.x + bbox.width + bbox.x;
	}

	let animateWidth: SVGAnimateElement | undefined;
	let animateFill: SVGAnimateElement | undefined;

	$: if (animate && animateWidth && animateFill) {
		animateWidth.beginElement();
		animateFill.beginElement();
	}
</script>

<svg bind:this={svg} width={svgWidth} height={40}>
	<defs>
		<pattern id={`pattern-${name}`} patternUnits="userSpaceOnUse" width="210" height="40">
			{#if textWidth && duration}
				<rect x="0" y="0" height="40" width="0" fill="#ff4136">
					<animate
						bind:this={animateWidth}
						begin="indefinite"
						attributeName="width"
						from="0"
						to={textWidth * level}
						dur={`${duration}s`}
						fill="freeze"
					/>

					<animate
						bind:this={animateFill}
						begin="indefinite"
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
		y="25"
		font-family="sans-serif"
		font-size={fontSize}
		font-weight="900"
		class="stroke-white stroke-1">{name}</text
	>
	<text
		x="0"
		y="25"
		font-family="sans-serif"
		font-size={fontSize}
		font-weight="900"
		fill={`url(#pattern-${name})`}
		class="stroke-white stroke-1">{name}</text
	>
</svg>
