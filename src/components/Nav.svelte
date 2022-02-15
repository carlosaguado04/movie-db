<script>


</script>

<nav>
	<div class="logo-container">
		<a data-blobity-tooltip="Home" href="/">AMDB</a>
	</div>
	<ul class="nav-links">
		<li  class="nav-link" >
			<a data-blobity-tooltip="About"   href="/about">
				<ion-icon name="information-circle"></ion-icon>
			</a>
		</li>
		<li class="nav-link">
			<a data-blobity-tooltip="Movies"  href="/movies">
				<ion-icon name="videocam"></ion-icon>
			</a>
		</li>
		<li class="nav-link">
			<a data-blobity-tooltip="Series"   href="/series">
				<ion-icon name="tv"></ion-icon>
			</a>
		</li>
	</ul>
</nav>

<style>
	nav {
		display: flex;
		min-height: 10vh;
		align-items: center;
		justify-content: space-around;
		list-style: none;
		z-index: 999;
	}

	.nav-link a {
		font-size: 2.5rem;
		font-family: 'Josefin Sans', sans-serif;
		color: white;
		text-decoration: none;

	}

	.nav-links {
		display: flex;
		width: 30%;
		justify-content: space-between;
		z-index: 999;
		list-style: none;
	}

	.nav-link a:hover {
		color: #1BFF83;
	}

	.logo-container {
		width: 70%;
		display: flex;
	}

	.logo-container a {
		font-size: 2.5rem;
		font-weight: bold;
		font-family: 'Josefin Sans', sans-serif;
		color: white;
		text-decoration: none;
		transition: ease-in-out 200ms;
	}

	.logo-container a:hover {
		color: rgb(27, 255, 131);
	}


</style>
