<script context="module">
	export async function load({ fetch }) {
		const res = await fetch(
			`https://api.themoviedb.org/3/movie/popular?api_key=29fe3343109db62f7473a92c31283a1f&language=en-US&page=2`
		);

		const data = await res.json();
		if (res.ok) {
			return {
				props: { popular: data.results }
			};
		}
	}
</script>

<script>
	import MovieCard from '../components/MovieCard.svelte';
	export let popular;
	import { fly } from 'svelte/transition';

</script>

<div in:fly={{ y: 50, duration: 500, delay: 500 }} out:fly={{ duration: 500 }} class="title">
	<h3>Popular Now</h3>
</div>
<div
	in:fly={{ y: 50, duration: 500, delay: 500 }}
	out:fly={{ duration: 500 }}
	class="popular-movies"
>
	{#each popular as movie}
		<MovieCard {movie} />
	{/each}
</div>

<style>
	.title {
		width: 100%;
		display: flex;
		justify-content: center;
		padding: 2rem 0;
	}

	.popular-movies {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
		grid-column-gap: 1rem;
		grid-row-gap: 2rem;
	}
</style>
