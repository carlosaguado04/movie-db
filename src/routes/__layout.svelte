<script>
	import global from '../global.css';
	import Nav from '../components/Nav.svelte';
	import Footer from '../components/Footer.svelte';

</script>

<svelte:head>
	<title>All Movies & Series</title>
	<link rel="icon" href="https://img.icons8.com/material-outlined/24/000000/movie.png" />
	<script src="https://kit.fontawesome.com/0b3d005b45.js" crossorigin="anonymous"></script>
</svelte:head>


<Nav />
<slot />
<Footer/>

