<script>
	let inputValue = '';
	let active = false;
	import { goto } from '$app/navigation';
	import { fly } from 'svelte/transition';

	function cancelInactive() {
		if (inputValue) {
			active = true;
		} else {
			active = false;
		}
	}

	function submitSearch() {
		goto('/search/' + inputValue);
	}
</script>

<div class="search-form">
	<form on:submit|preventDefault={submitSearch} class="search">
		{#if !active}
			<label
				in:fly={{ y: -10, duration: 500 }}
				out:fly={{ y: -10, duration: 500 }}
				for="search_movie">Search Movies and Series</label
			>
		{/if}
		<input
			on:blur={cancelInactive}
			on:focus={() => (active = true)}
			bind:value={inputValue}
			name="search_movie"
			type="text"
			class={active ? 'selected' : ''}
		/>
		{#if inputValue}
			<button in:fly={{ duration: 500 }} out:fly={{ duration: 500 }}>Search</button>
		{/if}
	</form>
</div>

<style>
	.search-form {
		width: 100%;
		display: flex;
		justify-content: center;
	}

	.search {
		position: relative;
		width: 30%;
		margin: 1rem;
	}

	button {
		font-size: 0.7rem;
		padding: 0rem 1rem;
		background: rgb(95, 205, 249);
		color: #333;
		font-weight: bold;
		border: none;
		position: absolute;
		bottom: 50%;
		right: 0;
		transform: translate(0, 50%);
		height: 100%;
		border-top-right-radius: 10px;
		border-bottom-right-radius: 10px;
		cursor: pointer;
	}

	input {
		width: 100%;
		border: none;
		font-size: 1rem;
		font-family: 'Josefin Sans', sans-serif;
		outline: none;
		color: rgb(255, 255, 255);
		padding: 0.5rem 0.1rem;
		transition: background 0.75s ease-out;
		font-weight: bold;
		background: rgba(63, 63, 63, 0);
		border-radius: 10px;
		padding: 1rem;
	}

	label {
		position: absolute;
		font-size: 0.8rem;
		top: 50%;
		left: 20%;
		transform: translate(0, -50%);
		pointer-events: none;
		color: rgb(255, 255, 255);
		padding: 0rem 1rem;
		text-transform: uppercase;
	}

	input.selected {
		background: rgb(50, 50, 50);
	}
</style>
