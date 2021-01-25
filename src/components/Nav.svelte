<script>
import IoLogoTwitter from "svelte-icons/io/IoLogoTwitter.svelte";
import MdHome from "svelte-icons/md/MdHome.svelte";
import GoSearch from "svelte-icons/go/GoSearch.svelte";
import MdNotificationsNone from "svelte-icons/md/MdNotificationsNone.svelte";
import MdMailOutline from "svelte-icons/md/MdMailOutline.svelte";
import MdBookmarkBorder from "svelte-icons/md/MdBookmarkBorder.svelte";
import TiThListOutline from "svelte-icons/ti/TiThListOutline.svelte";
import MdPersonOutline from "svelte-icons/md/MdPersonOutline.svelte";
import IoMdMore from "svelte-icons/io/IoMdMore.svelte";
import FaHashtag from "svelte-icons/fa/FaHashtag.svelte";
import FeatherPen from "./Icons/FeatherPen.svelte";
import Avatar from "./Avatar.svelte";
import Button from "./Button.svelte";
import Icon from "./Icons/Icon.svelte";

const mobileMenu = [
	{ name: "Home", component: MdHome },
	{ name: "Search", component: GoSearch },
	{ name: "Notifications", component: MdNotificationsNone },
	{ name: "Messages", component: MdMailOutline },
	{ name: "Bookmarks", component: MdBookmarkBorder },
	{ name: "Lists", component: TiThListOutline },
	{ name: "Profile", component: MdPersonOutline },
	{ name: "More", component: IoMdMore },
];

const exploreMenu = { name: "explore", component: FaHashtag };
</script>

<nav class="navigator">
	<div class="navigator-wrapper">
		<div class="navigator-wrapper-wrapper">
			<div class="navigator-wrapper-wrapper-wrapper">
				<div class="main-menu">
					<div class="twitter-logo">
						<div class="icon-main m-auto">
							<a
								href="https/twitter.com/anakagungcorp"
								class="icon-twitter"
							>
								<span
									style="width: 30px; height: 30px; color: var(--yellow); transform: translate(-2px, 1px); position: absolute; top: 0; left: 0;"
								>
									<IoLogoTwitter />
								</span>
								<span
									style="width: 30px; height: 30px; color: var(--magenta); transform: translate(2px, -1px); position: absolute; top: 0; left: 0;"
								>
									<IoLogoTwitter />
								</span>
								<span
									style="width: 30px; height: 30px; color: var(--cyan); position: absolute; top: 0; left: 0;"
								>
									<IoLogoTwitter />
								</span>
							</a>
						</div>
					</div>
					<div class="menu-wrapper">
						<ul class="menu">
							{#each mobileMenu as menu}
								<li class="menu-list">
									<div class="icon menu-icon">
										<svelte:component
											this="{menu.component}"
										/>
									</div>
									<p class="menu-title">{menu.name}</p>
								</li>
							{/each}
						</ul>
					</div>
					<div class="cta">
						<a href="#" style="text-decoration: none;">
							<div class="rounded pen">
								<div class="icon cta-tweet-mobile">
									<FeatherPen />
								</div>
								<div>
									<button class="cta-tweet">Tweet</button>
								</div>
							</div>
						</a>
					</div>
				</div>
				<!-- TODO: CREATE AVATAR ON BIGGER SCREEN -->
				<div class="follow-card">
					<Avatar
						src="/images/avatar_temp4.jpg"
						alt="jonny silverhand"
						size="{50}"
					/>
					<div class="follow-data">
						<p>Jonny Silverhand</p>
						<p>@jsh</p>
					</div>
					<div class="follow-cta-wrapper">
						<Icon size="{16}">
							<IoMdMore />
						</Icon>
					</div>
				</div>
			</div>
		</div>
	</div>
</nav>

<style>
.icon-twitter {
	color: var(--cyan);
	position: relative;
}

.m-auto {
	margin: auto;
}

.pen {
	padding: 10px;
	background: var(--cyan);
	box-shadow: 0 0 10px 0 var(--cyan);
}

.rounded {
	border-radius: 9999px;
}

.navigator {
	display: flex;
	flex-basis: auto;
	flex-direction: column;
	flex-shrink: 0;
	min-height: 0px;
	min-width: 0px;
	position: relative;
	user-select: none;
	z-index: 3;
	align-items: flex-end;
	flex-grow: 1;
}

.navigator-wrapper {
	user-select: none;
	align-items: stretch;
	display: flex;
	flex-basis: auto;
	flex-direction: column;
	flex-shrink: 0;
	position: relative;
	z-index: 0;
	width: 88px;
}

.navigator-wrapper-wrapper {
	display: flex;
	flex-basis: auto;
	flex-direction: column;
	flex-shrink: 0;
	min-height: 0px;
	min-width: 0px;
	z-index: 0;
	position: fixed;
	top: 0px;
	backface-visibility: hidden;
	height: 100%;
}

.navigator-wrapper-wrapper-wrapper {
	align-items: stretch;
	display: flex;
	flex-basis: auto;
	flex-direction: column;
	flex-shrink: 0;
	min-height: 0px;
	min-width: 0px;
	position: relative;
	z-index: 0;
	padding-left: 10px;
	padding-right: 10px;
	width: 88px;
	height: 100%;
	justify-content: space-between;
	overflow-y: auto;
}

.main-menu {
	display: flex;
	flex-basis: auto;
	flex-direction: column;
	flex-shrink: 0;
	min-height: 0px;
	min-width: 0px;
	position: relative;
	z-index: 0;
	align-items: center;
}

.twitter-logo {
	min-width: 49px;
	min-height: 49px;
	padding: 2px 0;
	display: flex;
	justify-content: center;
	align-items: center;
}

.icon {
	width: 28px;
	height: 28px;
	color: var(--red);
}

.icon-main {
	width: 45px;
	height: 30px;
}

.menu-wrapper {
	padding-top: 8px;
	padding-bottom: 8px;
}

.menu {
	list-style-type: none;
}

.menu-list {
	display: flex;
	align-items: center;
	justify-content: center;
	column-gap: 10px;
	padding: 8px;
	cursor: pointer;
}

.menu-list:hover {
	background: var(--red-light-4);
	color: var(--cyan);
	clip-path: polygon(
		0 0,
		20% 0,
		25% 7%,
		45% 7%,
		50% 0,
		95% 0,
		100% 15%,
		100% 100%,
		0 100%
	);
}

.menu-list:hover .menu-icon {
	color: var(--cyan);
}

.menu-title {
	display: none;
	font-size: 20px;
	font-weight: 600;
}

.cta-tweet {
	display: none;
	background: none;
	color: var(--blue);
	font-weight: 600;
	outline: none;
	border: none;
	font-size: 20px;
	font-family: inherit;
	text-decoration: none;
	margin: auto;
	cursor: pointer;
}

.follow-card {
	width: 90%;
	display: flex;
	justify-content: space-around;
	align-items: flex-start;
	padding: 12px;
	column-gap: 12px;
	clip-path: polygon(0 0, 100% 0, 100% 80%, 93% 100%, 0 100%);
}

.follow-card:hover {
	background-color: var(--red-dark-4);
	color: var(--cyan);
}

.follow-data {
	flex-grow: 2;
	cursor: pointer;
	display: none;
}

.follow-cta-wrapper {
	display: none;
}

@media only screen and (min-width: 1004px) {
	.menu-title {
		display: block;
	}

	.menu > li {
		justify-content: flex-start;
	}

	.navigator-wrapper,
	.navigator-wrapper-wrapper-wrapper {
		width: 275px;
	}

	.cta {
		justify-self: stretch;
		width: 80%;
	}

	.cta-tweet {
		display: block;
	}

	.cta-tweet-mobile {
		display: none;
	}

	.follow-data,
	.follow-cta-wrapper {
		display: block;
	}
}
</style>
