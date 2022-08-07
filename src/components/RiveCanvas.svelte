<script>
	import { Rive } from "@rive-app/canvas";
	import { onMount } from 'svelte';
    /** @type {string}*/
	export let source;
	export let sourceWidth = 500
	export let sourceHeight = 500;
	// TODO: Add output scale option
	// export let outputScale = 100

	let canvas;
	onMount(() => {
		new Rive({
			src: source,
			canvas: canvas,
			autoplay: true
		});
	});
</script>

<div id=canvas>
	<canvas width={sourceWidth} height={sourceHeight} id=canvas bind:this={canvas}></canvas>
</div>

<style>

	#canvas{
	/* border: solid 1px blue;   */
	text-align: center;
	display: inline;
	width: 80%;
}

</style>

