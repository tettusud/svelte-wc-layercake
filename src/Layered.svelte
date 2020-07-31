<script>
	// 	Note: Due to REPL limitations, full responsiveness may not work here. Download the example from here or from the website (https://layercake.graphics/example/MapSvg) and run locally to get all features.
	
	import { LayerCake, Svg, Html } from 'layercake';
	import { feature } from 'topojson';
	import { geoAlbersUsa } from 'd3-geo';

	import Map from './Map-svg.svelte';
	import Tooltip from './Tooltip.svelte';

	import usStates from './us-states-topojson.js';

	const geojson = feature(usStates, usStates.objects.collection);

	let evt;
	let hideTooltip = true;
</script>

<style>
	.chart-container {
		width: 100%;
		height: 100%;
	}
</style>

<div class="chart-container">
	<LayerCake
		data={geojson}
	>
		<Svg>
			<Map
				projection={geoAlbersUsa}

				on:mousemove={event => evt = hideTooltip= event}
				on:mouseout={() => hideTooltip = true}
			/>
		</Svg>

		<Html
			pointerEvents={false}
		>
			{#if hideTooltip !== true}
				<Tooltip
					{evt}
					let:detail
				>
					{#each Object.entries(detail.props) as [key, value]}
						<div class="row"><span>{key}:</span> {value}</div>
					{/each}
				</Tooltip>
			{/if}
		</Html>
	</LayerCake>
</div>
