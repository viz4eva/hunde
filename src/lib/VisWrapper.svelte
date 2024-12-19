<script>
	import Vis from './Vis.svelte';
	import { dogs } from '$lib/utils/loadDogs';

	const breeds = [
		'Mops',
		'Golden Retriever',
		'Dachshund',
		'Zwergspitz',
		'Bolonka Zwetna',
		'Border Collie',
		'Beagle',
		'Pudel',
		'Lagotto Romagnolo',
		'Pinscher'
	];

	let dogsByBreed = breeds.map((breed) => ({
		breed,
		filteredDogs: dogs
			.filter((dog) => dog['RASSE1'] === breed)
			.sort((a, b) => {
				if (+a['ALTER'].split('-')[0] !== +b['ALTER'].split('-')[0]) {
					return +a['ALTER'].split('-')[0] - +b['ALTER'].split('-')[0];
				}

				return 2024 - +a['GEBURTSJAHR_HUND'] - (2024 - +b['GEBURTSJAHR_HUND']);
			})
	}));
</script>

{#each dogsByBreed as { breed, filteredDogs }}
	<div class="wrapper"><Vis {breed} {filteredDogs} /></div>
{/each}
