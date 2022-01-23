<script>
	export let movie;
</script>

<div class="page">
	<div class="movie-card">
		<a sveltekit:prefetch sveltekit:noscroll href={'/movie/' + movie.id}>
			<img src={'https://image.tmdb.org/t/p/w500' + movie.poster_path} alt={movie.title} /></a
		>
		<div class="description">
			<h2>{movie.title}</h2>
			<p>{movie.release_date}</p>
		</div>
	</div>
</div>

<style>
	img {
		width: 100%;
		object-fit: cover;
		border-radius: 1rem;
		margin-bottom: 1rem;
		transition: ease 200ms;
	}

	img:hover {
		transform: scale(1.05);
		box-shadow: 0 0 11px rgba(255, 255, 255, 0.3);
	}

	h2 {
		font-size: 0.9rem;
	}

	.description {
		height: 5vh;
	}

	p {
		font-size: 0.7rem;
	}

	.movie-card {
		display: flex;
		flex-direction: column;
		justify-content: space-around;
		padding: 1rem;
	}
</style>
