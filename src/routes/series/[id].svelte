<script context="module">
	export async function load({ fetch, params }) {
		const res = await fetch(
			`https://api.themoviedb.org/3/tv/${params.id}?api_key=29fe3343109db62f7473a92c31283a1f&language=en-US`
		);

		const seriesDetail = await res.json();
		if (res.ok) {
			console.log(seriesDetail);
			return {
				props: { seriesDetail }
			};
		}
	}
</script>

<script>
	export let seriesDetail;
	import { fly } from 'svelte/transition';
</script>

<div
	class="series-detail"
	in:fly={{ y: 50, duration: 500, delay: 500 }}
	out:fly={{ duration: 500 }}
>
	<div class="img-container">
		<img
			src={'https://image.tmdb.org/t/p/original' + seriesDetail.backdrop_path}
			alt={seriesDetail.title}
		/>
	</div>
	<div class="txt-container">
		<h1>{seriesDetail.name}</h1>
		<p class="overview">{seriesDetail.overview}</p>
		<p>
			<span>Release date:</span>
			{seriesDetail.first_air_date} <br />
			<span>Origin:</span>
			{seriesDetail.origin_country} <br />
			<span>Rating:</span>
			{seriesDetail.vote_average} <br />
		</p>
	</div>
</div>


<style>
	h1 {
		padding: 1rem  2rem;
	}

	p {
		padding: 1rem ;
		font-size: 1rem;
		text-align: justify;
	}

	.img-container {
		width: 100%;
		display: flex;
		justify-content: center;
	}

	img {
		width: 100%;
		border-radius: 1rem;
		transition: 200ms ease-in-out;
		position: relative;
	}

	.series-detail {
		margin: 2rem 20%;
		height: 75vh;
	}

	span {
		font-weight: bold;
	}
</style>
