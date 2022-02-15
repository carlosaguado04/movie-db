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
				>Search for Movies and Series</label
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
			<button data-no-blobity in:fly={{ duration: 500 }} out:fly={{ duration: 500 }}
				><i class="fa-solid fa-magnifying-glass"></i></button
			>
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
		width: 50%;
		margin: 1rem;
	}

	button {
		font-size: 1.5rem;
		padding:  1rem;
		background: lightgreen;
		color: #333;
		font-weight: bold;
		border: none;
		position: absolute;
		bottom: 50%;
		right: 0;
		transform: translate(0, 50%);
		height: 99%;
		border-top-right-radius: 10px;
		border-bottom-right-radius: 10px;
		cursor: pointer;
	}

	input {
		width: 100%;
		border: 1px solid lightgreen;
		font-size: 1rem;
		font-family: 'Josefin Sans', sans-serif;
		outline: none;
		color: lightgreen;
		transition: background 0.75s ease-out;
		font-weight: bold;
		background: rgba(63, 63, 63, 0);
		border-radius: 10px;
		padding: 1rem;
	}

	label {
		position: absolute;
		font-size: 0.8rem;
		font-weight: 700;
		top: 50%;
		left: 50%;
		transform: translate(-50%, -50%);
		pointer-events: none;
		color: lightgreen;
		padding:  1rem;
		text-transform: uppercase;
	}

	i {
		background: lightgreen;
		border-top-left-radius: 10px;
		border-bottom-left-radius: 10px;
		color: rgb(51, 51, 51);
	}

	input.selected {
		background: rgb(51, 51, 51);
	}
</style>
