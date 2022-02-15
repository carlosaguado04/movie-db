<script>
	import { fly } from 'svelte/transition';
	import SearchMovies from '../components/SearchMovies.svelte';
	import Blobity from 'blobity';
	import { browser } from '$app/env';

	if (browser){
	const options = {
		color: 'rgb(51, 51, 51)',
		zIndex: '1',
		dotColor: 'lightgreen',
		fontColor: '#1BFF83',
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

</body>

<style>
	.main {
		height: 80vh;
		display: flex;
		justify-content: center;
		align-items: center;
	}
</style>
