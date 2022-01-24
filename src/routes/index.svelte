<script context="module">
	export async function load({ fetch }) {
		const res = await fetch(
			`https://api.themoviedb.org/3/movie/popular?api_key=29fe3343109db62f7473a92c31283a1f&language=en-US&page=1`
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
	import Footer from '../components/Footer.svelte';
	export let popular;
	import { fly } from 'svelte/transition';
	import SearchMovies from '../components/SearchMovies.svelte';
</script>

<section class="main" in:fly={{ y: 50, duration: 500, delay: 500 }} out:fly={{ duration: 500 }}>
	<SearchMovies />
</section>
<Footer />

<style>
	.main {
		height: 75vh;
		display: flex;
		justify-content: center;
		align-items: center;
	}
</style>
