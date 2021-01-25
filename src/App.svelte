<script>
import { onMount } from "svelte";
import { fade } from "svelte/transition";

import Cursor from "./components/Cursor.svelte";
import Footer from "./components/Footer.svelte";
import Nav from "./components/Nav.svelte";
import NavHor from "./components/NavHor.svelte";
import Spacer from "./components/Spacer.svelte";
import TweetForm from "./components/TweetForm.svelte";
import TwitterCard from "./components/TwitterCard.svelte";
import TwitterCard1 from "./components/TwitterCard1.svelte";
import TwitterCard2 from "./components/TwitterCard2.svelte";
import Layout from "./Layout.svelte";

let innerHeight;
let visible = false;

onMount(() => (visible = true));
</script>

<svelte:window bind:innerHeight />

<div class="container" style="min-height: {innerHeight}">
	<Nav />
	<Layout>
		<section class="content">
			<div class="content-wrapper">
				<NavHor />
				<TweetForm />
				<Spacer
					size="{{ width: '100%', height: '8px' }}"
					innerShadow="{true}"
				/>
				<div>
					{#if visible}
						<div transition:fade="{{ duration: 1000 }}">
							<TwitterCard />
							<TwitterCard1 />
							<TwitterCard />
							<TwitterCard2 />
							<TwitterCard1 />
							<TwitterCard1 />
						</div>
					{/if}
				</div>
			</div>
		</section>
		<Footer />
	</Layout>
</div>

<!-- <Cursor /> -->
<style>
/* :global(*) {
	cursor: none;
} */
.container {
	display: flex;
	background: linear-gradient(
		170deg,
		rgba(255, 20, 20, 0.6) -80%,
		transparent
	);
	font-size: 15px;
	align-items: stretch;
	flex-basis: auto;
	flex-shrink: 0;
	min-width: 0px;
	position: relative;
	pointer-events: auto;
	width: 100%;
	z-index: 0;
	flex-direction: row;
}

.content {
	display: flex;
	flex-basis: auto;
	flex-shrink: 0;
	min-width: 0px;
	position: relative;
	z-index: 0;
	min-height: 100%;
	width: 100%;
	flex-direction: row;
	align-items: stretch;
	justify-content: space-between;
}

.content-wrapper {
	display: flex;
	flex-basis: auto;
	flex-direction: column;
	flex-shrink: 0;
	min-width: 0px;
	position: relative;
	width: 100%;
	z-index: 1;
	max-width: 600px;
	border-left: 1px solid var(--cyan);
	border-right: 1px solid var(--cyan);
}

@media only screen and (min-width: 1004px) {
	.content {
		width: 660px;
	}
}
</style>
