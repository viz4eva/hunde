<script>
	import VisWrapper from '$lib/VisWrapper.svelte';
</script>

<h1>Do the people of Zürich own dogs that are similar to them?</h1>
<p>
	It's a cliché that dogs always look like their owners. Given some data about the age and gender of dogs and their owners, we cannot see whether that
	is true, but we can sure compare whether owners tend to own dogs that are of equivalent age.
	Also, this might differ for different breeds. I selected ten breeds that can be found to a
	manageable amount in Zürich.
	<br />
	<br />
	The owner's age is drawn as a rectangle (spanning a decade, as we don't have more fine-grained information
	in the data), the dog's age as a circle. Also, the symbols are colored in
	<span class="orange"> orange</span> when the being is female and in
	<span class="green">green</span>
	when it's male.
	<br />
	<br />I used R for the data exploration and d3.js for implementing the visualizations as an exercise within an application assignment. The data is most probably more or less fictional but fun &#128054;
</p>

<VisWrapper />

<style>
	.orange {
		color: orange;
	}

	.green {
		color: green;
	}
</style>
