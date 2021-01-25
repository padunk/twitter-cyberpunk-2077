<script>
import MdMoreVert from "svelte-icons/md/MdMoreVert.svelte";
import Icon from "./Icons/Icon.svelte";

export let trend;
export let numberOfTweets;
export let listMouseOver;
</script>

<li class="trends-lists" on:mouseover="{listMouseOver}">
	<a href="https://anakagung.com" target="_blank" rel="noopener noreferrer">
		<div>
			<span>{trend}</span>
			<Icon size="{18}">
				<MdMoreVert />
			</Icon>
		</div>
		<p>{numberOfTweets} Tweets</p>
	</a>
</li>

<style>
div {
	display: flex;
	justify-content: space-between;
	align-items: center;
}

a:link,
a:visited {
	text-decoration: none;
	color: var(--yellow);
	padding: 12px;
	display: flex;
	flex-direction: column;
	line-height: 1.89;
}

a:hover,
a:active {
	background: var(--secondary);
}

li:not(:last-child) {
	border-bottom: 1px solid var(--cyan);
}

p {
	color: var(--secondary-light);
	font-size: 14px;
}
</style>
