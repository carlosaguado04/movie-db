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
	import PopularMovies from '../components/PopularMovies.svelte';
	export let popular;
	import global from '../global.css';
</script>

<section><PopularMovies {popular} /></section>
