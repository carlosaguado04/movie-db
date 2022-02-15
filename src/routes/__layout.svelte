<script>
	import global from '../global.css';
	import Nav from '../components/Nav.svelte';

</script>

<svelte:head>
	<title>All Movies & Series</title>
	<link rel="icon" href="https://img.icons8.com/material-outlined/24/000000/movie.png" />
	<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" integrity="sha512-9usAa10IRO0HhonpyAIVpjrylPvoDwiPUiKdWk5t3PyolY1cOd4DSE0Ga+ri4AuTroPR5aQvXU9xC6qOPnzFeg==" crossorigin="anonymous" referrerpolicy="no-referrer" />
</svelte:head>


<Nav />

<main>
	<slot />
</main>
