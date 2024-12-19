<script>
	export let breed, filteredDogs;
	import * as d3 from 'd3';
	const width = 1000;
	const height = 300;
	const marginTop = 20;
	const marginBottom = 20;
	const marginLeft = 30;
	const glyphWidth = 5;
	const radius = 3;
	const y = d3.scaleLinear([0, 100], [height - marginBottom, marginTop]);
	let yAxis = d3.axisLeft(y);
	/**
	 * @type {SVGGElement}
	 */
	let yAxisGroup;

	$: {
		d3.select(yAxisGroup).call(yAxis);
	}
</script>

<h3>{breed}</h3>

<svg {width} {height}>
	<g bind:this={yAxisGroup} transform={`translate(${marginLeft},0)`}/>
	<g>
		{#each filteredDogs as d, i}
			<g>
				<line
					x1={i * glyphWidth + marginLeft + 10}
					y1={+y(d['ALTER'].split('-')[1])}
					x2={i * glyphWidth + marginLeft + 10}
					y2={y(2024 - +d['GEBURTSJAHR_HUND'])}
					stroke={d['GESCHLECHT_HUND'] === d['GESCHLECHT']
						? d['GESCHLECHT_HUND'] === 'w'
							? 'orange'
							: 'green'
						: 'grey'}
				/>
				<circle
					cx={i * glyphWidth + marginLeft + 10}
					cy={y(2024 - +d['GEBURTSJAHR_HUND'])}
					r={radius}
					fill={d['GESCHLECHT_HUND'] === 'w' ? 'orange' : 'green'}
				/>
				<rect
					x={i * glyphWidth + marginLeft + 10 - radius / 2}
					y={+y(d['ALTER'].split('-')[1])}
					width={radius}
					height={y(+d['ALTER'].split('-')[0]) - +y(+d['ALTER'].split('-')[1])}
					fill={d['GESCHLECHT'] === 'w' ? 'orange' : 'green'}
				/>
			</g>
		{/each}
	</g>
</svg>