<script>
	import global from '../global.css';
	import Nav from '../components/Nav.svelte';
</script>

<svelte:head>
	<title>All Movies & Seriess</title>
	<link rel="icon" href="https://img.icons8.com/material-outlined/24/000000/movie.png" />
	<link
		rel="stylesheet"
		href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css"
		integrity="sha512-Fo3rlrZj/k7ujTnHg4CGR2D7kSs0v4LLanw2qksYuRlEzO+tcaEPQogQ0KaoGN26/zrn20ImR1DfuLWnOo7aBA=="
		crossorigin="anonymous"
		referrerpolicy="no-referrer"
	/>
</svelte:head>

<Nav />

<main>
	<slot />
</main>
