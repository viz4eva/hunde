<script>
	import VisWrapper from '$lib/VisWrapper.svelte';
</script>

<div class="col">
	<img src="Hundi2.png" alt="dog illu" style="margin-top:30%; opacity:50%" />
	<div>
		<h1>Wie ähnlich sind sich Zürcher Hunde und ihre Besitzer? </h1>
		<p>
			Es ist ein bekanntes Klischee, dass Hunde und ihre Besitzer:innen sich oft ähneln. Anhand der Daten zu Alter und Geschlecht der Hunde und der zugehörigen Menschen können wir sehen, ob das zumindest in dieser Hinsicht zutreffen könnte. Ich habe beispielhaft zehn Hunderassen ausgewählt,
			die in Zürich in überschaubarer Häufigkeit anzutreffen sind.

			<br />
			<br />
			Das Alter des Besitzers ist als Rechteck gezeichnet (über ein Jahrzehnt, da keine genaueren
			Altersangaben vorliegen), das Alter des Hundes als Kreis. Außerdem sind die Symbole
			<span class="orange"> orange</span> gefärbt, wenn das Lebewesen weiblich ist, und
			<span class="green">grün</span>, wenn es männlich ist.

			<br />
			<br />Für die Datenexploration wurde R und für die Implementierung der Visualisierungen D3.js
			genutzt. Dieser Entwurft war eine Übung im Rahmen einer Bewerbungsaufgabe. Die Daten sind
			höchstwahrscheinlich mehr oder weniger fiktiv, aber lustig &#128054;
		</p>
	</div>
	<img src="Hundi3.png" alt="dog illu" style="opacity:50%" />
</div>

<VisWrapper />

<style>
	.orange {
		color: orange;
	}

	.green {
		color: green;
	}

	.col {
		display: grid;
		grid-template-columns: 15% 80% 5%;
	}
</style>
