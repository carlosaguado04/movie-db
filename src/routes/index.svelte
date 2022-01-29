<script>
	import Footer from '../components/Footer.svelte';
	import { fly } from 'svelte/transition';
	import SearchMovies from '../components/SearchMovies.svelte';
	import Blobity from 'blobity';

	const options = {
		color: 'rgb(55, 55, 55)',
		dotColor: 'pink',
		mode: 'bouncy',
		font: 'Josefin Sans',
		fontWeight: '700',
		fontColor: '#FFFFFF',
		fontSize: '20',
		focusableElementsOffsetX: '10',
		focusableElementsOffsetY: '10',
		radius: '10'
	};
	new Blobity(options);
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
