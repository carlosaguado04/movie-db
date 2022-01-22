<script context="module">
	export async function load({ fetch, params }) {
		const res = await fetch(
			`https://api.themoviedb.org/3/movie/${params.id}?api_key=29fe3343109db62f7473a92c31283a1f&language=en-US`
		);

		const movieDetails = await res.json();
		if (res.ok) {
			return {
				props: { movieDetails }
			};
		}
	}
</script>

<script>
	export let movieDetails;
	console.log(movieDetails);
</script>

<div class="movie-details">
	<div class="img-container">
		<img
			src={'https://image.tmdb.org/t/p/original' + movieDetails.backdrop_path}
			alt={movieDetails.title}
		/>
	</div>
	<div class="txt-container">
		<h1>{movieDetails.title}</h1>
	</div>
</div>
