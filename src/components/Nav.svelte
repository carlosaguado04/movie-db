<nav>
	<div class="logo-container">
		<a href="/">AMDB</a>
	</div>
	<ul class="nav-links">
		<li class="nav-link"><a href="/">Home</a></li>
		<li class="nav-link"><a href="/movies">Movies</a></li>
		<li class="nav-link"><a href="/series">Series</a></li>
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
		transition: ease 200ms;
	}

	.nav-links {
		display: flex;
		width: 30%;
		justify-content: space-between;
		border: 2px solid rgba(0, 0, 0, 0);
		list-style: none;
	}

	.nav-link a:hover {
		border-bottom: 2px solid #f2e863;
		color: #f2e863;
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
		color: orange;
	}
</style>
