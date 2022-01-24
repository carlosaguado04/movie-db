<script>
	import SeriesCard from './SeriesCard.svelte';

	export let popular;
</script>

<div class="title">
	<h3>Popular Now</h3>
</div>
<div class="popular-series">
	{#each popular as series}
		<SeriesCard {series} />
	{/each}
</div>

<style>
	.title {
		width: 100%;
		display: flex;
		justify-content: center;
		padding: 2rem 0;
	}

	.popular-series {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
		grid-column-gap: 1rem;
		grid-row-gap: 2rem;
	}
</style>
