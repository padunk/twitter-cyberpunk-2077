<script>
export let src;
export let alt;
export let size;
</script>

<div class="image" style="width:{size}px; height:{size}px">
	<div class="image-wrapper" style="width:{size - 2}px; height:{size - 2}px">
		<img src="{src}" alt="{alt}" />
	</div>
</div>

<style>
img {
	width: 100%;
	height: 100%;
	object-fit: cover;
}

.image-wrapper {
	overflow: hidden;
	margin: auto;
	clip-path: var(--clip-bottom-right-20-square);
	display: flex;
	justify-content: center;
	align-items: center;
}

.image {
	display: flex;
	flex-basis: auto;
	flex-direction: column;
	flex-shrink: 0;
	min-height: 0px;
	min-width: 0px;
	position: relative;
	z-index: 0;
	-webkit-box-align: center;
	align-items: center;
	justify-content: center;
	clip-path: var(--clip-bottom-right-20-square);
	background: var(--yellow);
}
</style>
