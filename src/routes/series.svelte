<script context="module">
	export async function load({ fetch }) {
		const res = await fetch(
			`https://api.themoviedb.org/3/tv/popular?api_key=29fe3343109db62f7473a92c31283a1f&language=en-US&page=1`
		);

		const data = await res.json();
		console.log(data);
		if (res.ok) {
			return {
				props: { popular: data.results }
			};
		}
	}
</script>

<script>
	import PopularSeries from '../components/PopularSeries.svelte';
	export let popular;
	import { fly } from 'svelte/transition';
</script>

<section in:fly={{ y: 50, duration: 500, delay: 500 }} out:fly={{ duration: 500 }}>
	<PopularSeries {popular} />

</section>
