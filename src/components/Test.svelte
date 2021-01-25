<script>
const { x, y, width, height } = element.getBoundingClientRect();
// so you don't have to write all that element.getBoundingClientRect() again
const el = {
	x,
	y,
	width,
	height,
};

// instead of
const el1 = {
	x: element.getBoundingClientRect().x,
	y: element.getBoundingClientRect().y,
	width: element.getBoundingClientRect().width,
	height: element.getBoundingClientRect().height,
};
</script>
