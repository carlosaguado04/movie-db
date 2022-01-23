<script>
	import { fly } from 'svelte/transition';
	import Footer from '../components/Footer.svelte';
</script>

<div in:fly={{ y: 50, duration: 500, delay: 500 }} out:fly={{ duration: 500 }} class="main-movies">
	<div class="coming-soon"><h1>Coming Soon</h1></div>
	<div class="loader-wrapper">
		<div class="loader-container">
			<h1 class="lt">&lt</h1>
			<h1 class="loader">/</h1>
			<h1 class="lt" id="ltNd">&lt</h1>
		</div>
	</div>
</div>
<Footer />

<style>
	.main-movies {
		height: 70vh;
		width: 100%;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		text-transform: uppercase;
	}

	.loader-container {
		font-size: 2.5em;
		font-weight: 700;
	}
	.loader-wrapper {
		width: 100%;
		display: flex;
		align-items: center;
	}
	.loader-container {
		width: 100%;
		display: flex;
		justify-content: center;
		position: relative;
	}
	.lt {
		width: 150px;
		position: absolute;
	}
	#ltNd {
		transform: rotateZ(180deg);
	}
	.loader {
		background: -webkit-linear-gradient(45deg, red, orange);
		-webkit-background-clip: text;
		-webkit-text-fill-color: transparent;
		position: absolute;
		transform: rotateX(0deg);
		transform-style: preserve-3d;
		animation: loading 1s ease-in-out infinite;
	}

	@keyframes loading {
		0% {
			transform: rotateX(0deg);
		}
		50% {
			transform: rotateX(180deg);
		}
		100% {
			transform: rotateX(360deg);
		}
	}
</style>
