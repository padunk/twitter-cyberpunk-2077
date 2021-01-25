<script>
export let size;
export let innerShadow = false;
</script>

<span
	style="display: inline-block; width:{size.width}; height:{size.height}; {innerShadow ? 'box-shadow: 0 -1px 4px 0 var(--cyan) inset, 0 1px 4px 0 var(--cyan) inset;' : ''}"
></span>

<style>
</style>
