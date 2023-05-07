<script lang="ts">
	export let name: string;
</script>

<svg width="100%" height="100%" viewBox="0 0 800 200">
	<defs>
		<pattern id="pattern" patternUnits="userSpaceOnUse" width="800" height="200">
			<rect x="0" y="0" height="200" width="0" fill="#ff4136">
				<animate attributeName="width" from="0" to="800" dur="2s" fill="freeze" />
				<animate
					attributeName="fill"
					values="#ff4136; #ff851b; #2ecc40"
					keyTimes="0; 0.6; 1"
					dur="2s"
					fill="freeze"
				/>
			</rect>
		</pattern>
	</defs>
	<text
		x="0"
		y="150"
		font-family="sans-serif"
		font-size="120"
		font-weight="900"
		fill="white"
		style="stroke: white; stroke-width: 1px;">{name}</text
	>
	<text
		x="0"
		y="150"
		font-family="sans-serif"
		font-size="120"
		font-weight="900"
		fill="url(#pattern)"
		style="stroke: white; stroke-width: 1px;">{name}</text
	>
</svg>
