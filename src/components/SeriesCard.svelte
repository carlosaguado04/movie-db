<script>
	export let series;
</script>

<div class="page">
	<div class="series-card">
		<a sveltekit:prefetch href={'/series/' + series.id}>
			<img src={'https://image.tmdb.org/t/p/w500' + series.poster_path} alt={series.title} /></a
		>
		<div class="description">
			<h2>{series.name}</h2>
			<p>{series.first_air_date}</p>
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

	.series-card {
		display: flex;
		flex-direction: column;
		justify-content: space-around;
		padding: 1rem;
	}
</style>
