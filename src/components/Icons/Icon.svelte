<script>
import { beforeUpdate } from "svelte";

export let size;
export let className = undefined;
export let color = "currentColor";

beforeUpdate(() => {
	className = className || undefined;
	color = color || "currentColor";
});
</script>

<span
	style="width:{size}px; height:{size}px; display: inline-block; color: {color}"
	class="{className}"
>
	<slot>
		<!-- optional fallback -->
	</slot>
</span>
