<nav>
	<div class="logo-container">
		<a data-blobity-tooltip="Home" data-blobity-font="" href="/">AMDB</a>
	</div>
	<ul class="nav-links">
		<li class="nav-link"><a href="/about">About</a></li>
		<li class="nav-link"><a href="/movies">Movies</a></li>
		<li class="nav-link"><a href="/series">TV Shows</a></li>
	</ul>
</nav>

<style>
	nav {
		display: flex;
		min-height: 10vh;
		align-items: center;
		justify-content: space-around;
		list-style: none;
	}

	.nav-link a {
		font-size: 1.25rem;
		font-weight: bold;
		font-family: 'Josefin Sans', sans-serif;
		color: white;
		text-decoration: none;
	}

	.nav-links {
		display: flex;
		width: 30%;
		justify-content: space-between;

		list-style: none;
	}

	.nav-link a:hover {
		color: rgb(27, 255, 131);
	}

	.logo-container {
		width: 70%;
		display: flex;
	}

	.logo-container a {
		font-size: 2rem;
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
