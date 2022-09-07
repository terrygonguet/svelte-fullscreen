<script lang="ts">
	import { useFullscreen } from "$lib"

	const { fullscreen, enter, exit, toggle } = useFullscreen()
</script>

<svelte:head>
	<title>@terrygonguet/svelte-fullscreen demo</title>
</svelte:head>

<main use:fullscreen on:fullscreenchange={console.log}>
	<h1>
		<a href="https://www.npmjs.com/package/@terrygonguet/svelte-fullscreen"
			>@terrygonguet/svelte-fullscreen</a
		> demo
	</h1>

	<button on:click={enter}>Go fullscreen</button>
	<button on:click={exit}>Exit fullscreen</button>
	<button on:click={toggle}>Toggle fullscreen</button>
</main>

<style>
	main {
		background-color: white;
	}

	main:fullscreen {
		border: 2px solid red;
	}
</style>
