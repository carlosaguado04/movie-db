<script>
	import global from '../global.css';
	import Nav from '../components/Nav.svelte';

</script>

<svelte:head>
	<title>All Movies & Series</title>
	<link rel="icon" href="https://img.icons8.com/material-outlined/24/000000/movie.png" />
	<script src="https://unpkg.com/ionicons@4.5.10-0/dist/ionicons.js"></script>
</svelte:head>


<Nav />

<main>
	<slot />
</main>
