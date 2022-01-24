<script context="module">
	export async function load({ fetch, params }) {
		const res = await fetch(
			`https://api.themoviedb.org/3/movie/${params.id}?api_key=29fe3343109db62f7473a92c31283a1f&language=en-US`
		);

		const movieDetail = await res.json();
		if (res.ok) {
			return {
				props: { movieDetail }
			};
		}
	}
</script>

<script>
	export let movieDetail;
	import Footer from '../../components/Footer.svelte';
	import { fly } from 'svelte/transition';
</script>

<div class="movie-detail" in:fly={{ y: 50, duration: 500, delay: 500 }} out:fly={{ duration: 500 }}>
	<div class="img-container">
		<img
			src={'https://image.tmdb.org/t/p/original' + movieDetail.backdrop_path}
			alt={movieDetail.title}
			class="in"
		/>
	</div>
	<div class="txt-container">
		<h1>{movieDetail.title}</h1>
		<p class="overview">{movieDetail.overview}</p>
		<p>
			<span>Release date:</span>
			{movieDetail.release_date} <br />
			<span>Budget:</span> ${movieDetail.budget} <br />
			<span>Rating:</span>
			{movieDetail.vote_average} <br />
			<span>Runtime: </span>
			{movieDetail.runtime}mins
		</p>
	</div>
</div>
<Footer />

<style>
	h1 {
		padding: 1rem 0rem 2rem;
	}

	p {
		padding: 1rem 0rem;
		font-size: 1.25rem;
		text-align: justify;
	}

	.img-container {
		width: 100%;
		display: flex;
		justify-content: center;
	}

	img {
		width: 80%;
		border-radius: 1rem;
		transition: 200ms ease-in-out;
		position: relative;
	}

	.movie-detail {
		margin: 2rem 20%;
	}

	span {
		font-weight: bold;
	}
</style>
