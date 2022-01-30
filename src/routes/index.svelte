<script>
	import Footer from '../components/Footer.svelte';
	import { fly } from 'svelte/transition';
	import SearchMovies from '../components/SearchMovies.svelte';
</script>

<section class="main" in:fly={{ y: 50, duration: 500, delay: 500 }} out:fly={{ duration: 500 }}>
	<SearchMovies />
</section>
<Footer />

<style>
	.main {
		height: 82.2vh;
		display: flex;
		justify-content: center;
		align-items: center;
	}
</style>
