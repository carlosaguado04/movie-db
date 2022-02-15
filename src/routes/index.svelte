<script>
	import Footer from '../components/Footer.svelte';
	import { fly } from 'svelte/transition';
	import SearchMovies from '../components/SearchMovies.svelte';
	import Blobity from 'blobity';
	import { browser } from '$app/env';

	if (browser){
	const options = {
		color: 'rgb(51, 51, 51)',
		zIndex: '998',
		dotColor: 'lightgreen',
		fontColor: '#ffffff',
		fontSize: '25',
		tooltipPadding: '15',
		font: 'Josefin Sans',
		fontWeight: '700',
		focusableElementsOffsetX: '15',
		focusableElementsOffsetY: '15'

	};
	new Blobity(options);
}


</script>
<body>
<section class="main" in:fly={{ y: 50, duration: 500, delay: 500 }} out:fly={{ duration: 500 }}>
	<SearchMovies />
</section>
<Footer />

</body>

<style>
	.main {
		height: 82.2vh;
		display: flex;
		justify-content: center;
		align-items: center;
	}
</style>
