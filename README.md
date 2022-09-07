# @terrygonguet/svelte-fullscreen

A very simple [Svelte](https://svelte.dev/) [action](https://svelte.dev/docs#template-syntax-element-directives-use-action) to make elements go [fullscreen](https://developer.mozilla.org/en-US/docs/Web/API/Fullscreen_API).

## Installation

```
npm install @terrygonguet/svelte-fullscreen
```

## Example

```svelte
<script>
	import { useFullscreen } from "@terrygonguet/svelte-fullscreen"

	const { fullscreen, enter, exit, toggle } = useFullscreen()
</script>

<svelte:window on:fullscreenchange={console.log} />

<!-- The <main> element will go fullscreen -->
<main use:fullscreen>
	<button on:click={enter}>Go fullscreen</button>
	<button on:click={exit}>Exit fullscreen</button>
	<button on:click={toggle}>Toggle fullscreen</button>
</main>

<style>
	main:fullscreen {
		border: 2px solid red;
	}
</style>
```

## Usage

Call the `useFullscreen` function in your component and `use:` the `fullscreen` property of the returned object on the element you want to go fullscreen. The `enter`, `exit` and `toggle` functions do what their names imply and return a promise that completes when the process is done, same as the underlying [Fullscreen API](https://developer.mozilla.org/en-US/docs/Web/API/Fullscreen_API).

## API

### `function useFullscreen`

```typescript
function useFullscreen(options?: FullscreenOptions): {
	fullscreen: Action
	enter(): Promise<void>
	exit(): Promise<void>
	toggle(): Promise<void>
}
```

### `type Fullscreenoptions`

See details on [MDN](https://developer.mozilla.org/en-US/docs/Web/API/Element/requestFullscreen).
