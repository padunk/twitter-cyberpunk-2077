<script>
import { afterUpdate } from "svelte";

import { spring } from "svelte/motion";

let coords = { x: 50, y: 50 };
coords.damping = 0.66;
coords.stiffness = 0.1;

let size = 40;

const debounce = (fn, time) => {
	let handle;
	if (handle) {
		clearTimeout(handle);
	}
	handle = setTimeout(fn, time);
};

function handleMouseMove(event) {
	coords = { ...coords, x: event.clientX, y: event.clientY };
}
</script>

<div
	style="width: {size}px; height: {size}px; top: {coords.y}px; left: {coords.x}px;"
	on:mousedown="{() => size.set(50)}"
	on:mouseup="{() => size.set(40)}"
></div>

<svelte:window on:mousemove="{(e) => debounce(handleMouseMove(e), 500)}" />

<style>
div {
	border-radius: 9999px;
	position: absolute;
	top: 0;
	left: 0;
	background: var(--blue);
	z-index: 999999;
}
</style>
