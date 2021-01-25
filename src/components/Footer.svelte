<script>
import GoSearch from "svelte-icons/go/GoSearch.svelte";
import IoMdSettings from "svelte-icons/io/IoMdSettings.svelte";
import Avatar from "./Avatar.svelte";
import Button from "./Button.svelte";
import Icon from "./Icons/Icon.svelte";
import Spacer from "./Spacer.svelte";
import TrendList from "./TrendList.svelte";

const trendLists = [
	{ trend: "#ReactJS", numberOfTweets: "1.9 M" },
	{ trend: "#ReactNative", numberOfTweets: "1402" },
	{ trend: "#Redux", numberOfTweets: "917" },
	{ trend: "#StyledComponents", numberOfTweets: "1.8 K" },
	{ trend: "#Firebase", numberOfTweets: "817" },
];

const toFollow = [
	{ name: "Abraham Anak Agung", handle: "@anakagungcorp" },
	{ name: "AlephJS", handle: "@alephjs" },
	{ name: "V", handle: "@v" },
];

let marTop = 0;

const listMouseOver = (i) => {
	const shift = 75;
	marTop = i * shift;
};
</script>

<footer>
	<section>
		<div class="messages"></div>

		<section>
			<div class="search">
				<form action="" class="search-form">
					<input type="text" class="search-text" id="search-text" />
					<span class="icon-wrapper">
						<Icon size="{16}">
							<GoSearch />
						</Icon>
					</span>
					<span class="search-text-bg"></span>
				</form>
			</div>
			<Spacer size="{{ width: '100%', height: '12px' }}" />
			<div class="trends">
				<div class="trends-wrapper">
					<div class="trends-header">
						<span class="trends-title">New Trends for you</span>
						<span>
							<Icon size="{18}">
								<IoMdSettings />
							</Icon>
						</span>
					</div>
					<div class="trends-list-wrapper">
						<p class="trends-subtitle">Trending in My Stack</p>
						<ul class="trends-list">
							{#each trendLists as trend, idx}
								<TrendList
									trend="{trend.trend}"
									numberOfTweets="{trend.numberOfTweets}"
									listMouseOver="{() => listMouseOver(idx)}"
								/>
							{/each}
						</ul>
					</div>
				</div>
			</div>
			<Spacer size="{{ width: '100%', height: '12px' }}" />
			<div class="to-follow">
				<div class="trends-wrapper">
					<div class="trends-header to-follow-header">
						<span class="trends-title">Inspiring People</span>
					</div>
					<div class="trends-list-wrapper">
						<ul class="trends-list">
							{#each toFollow as people}
								<li class="to-follow-lists">
									<div class="follow-card">
										<Avatar
											src="/images/avatar_temp{Math.floor(Math.random() * 5 + 1)}.jpg"
											alt="ok"
											size="{45}"
										/>
										<div class="follow-data">
											<p>{people.name}</p>
											<p>{people.handle}</p>
										</div>
										<div class="follow-cta-wrapper">
											<Button>Follow</Button>
										</div>
									</div>
								</li>
							{/each}
						</ul>
					</div>
				</div>
			</div>
			<Spacer size="{{ width: '100%', height: '12px' }}" />
			<div class="footer">
				<ul class="other-list">
					<li>Terms of Service</li>
					<li>Privacy Policy</li>
					<li>Cookie Policy</li>
					<li>Ads info</li>
					<li>More</li>
				</ul>
				<p>© 2021 Twitter, Inc.</p>
			</div>
		</section>
	</section>
</footer>

<style>
footer {
	display: none;
}

section {
	padding: 4px;
	width: 350px;
}

.search-form {
	outline: 1px solid white;
	padding: 12px;
	clip-path: var(--clip-bottom-right-20);
	position: relative;
}

.icon-wrapper {
	position: relative;
	z-index: 1;
}

.search-text {
	position: absolute;
	width: calc(100% - 2px);
	height: calc(100% - 2px);
	padding: 8px;
	padding-left: 40px;
	border: none;
	outline: none;
	background: var(--red-dark-4);
	color: var(--cyan);
	font-size: 18px;
	font-family: inherit;
	clip-path: var(--clip-bottom-right-20);
	top: 50%;
	left: 50%;
	transform: translate(-50%, -50%);
}

.search-text:focus {
	background: var(--red-dark-3);
}

.search-text-bg {
	position: absolute;
	background-color: var(--red-light-4);
	inset: 0;
	width: 100%;
	height: 100%;
	clip-path: var(--clip-bottom-right-20);
	z-index: -1;
}

.search-text:focus ~ .search-text-bg {
	background: var(--cyan);
}

.search-text:focus ~ .icon-wrapper {
	color: var(--cyan);
}

.trends {
	background: var(--primary);
	border: 1px solid var(--secondary);
	padding-top: 16px;
	width: 100%;
	clip-path: polygon(
		0% 0%,
		10% 0%,
		15% 2%,
		40% 2%,
		45% 0%,
		100% 0%,
		100% 100%,
		0% 100%
	);
}

.trends-wrapper {
	width: inherit;
	position: relative;
}

.trends-wrapper::before {
	content: "";
	background: var(--magenta-dim);
	width: 5px;
	position: absolute;
	bottom: 0;
	left: 0;
	transform: translate(-5px, 3px);
	height: 50%;
	clip-path: polygon(0% 0%, 100% 0%, 100% 100%, 0% 95%);
}

.trends-header {
	display: flex;
	justify-content: space-between;
	align-items: center;
	padding: 0 16px;
	font-size: 20px;
	font-weight: 600;
}

.trends-subtitle {
	font-size: 16px;
	border-bottom: 1px solid var(--cyan);
	padding: 4px 16px;
	padding-bottom: 8px;
}

.trends-list {
	list-style-type: none;
}

.to-follow {
	display: flex;
	justify-content: stretch;
	width: 100%;
	border: 1px solid var(--magenta);
}

.to-follow-header {
	padding: 12px;
	border-bottom: 1px solid var(--magenta);
}

.follow-card {
	width: 100%;
	display: flex;
	justify-content: space-around;
	align-items: flex-start;
	padding: 12px;
	column-gap: 12px;
}

.follow-card:hover {
	background-color: var(--red-dark-4);
	color: var(--cyan);
}

.to-follow-lists:not(:last-child) {
	border-bottom: 1px solid var(--magenta);
}

.follow-data {
	flex-grow: 2;
	cursor: pointer;
}

.other-list {
	list-style-type: none;
	display: flex;
	flex-wrap: wrap;
	column-gap: 16px;
	color: var(--secondary-light);
}

@media only screen and (min-width: 1004px) {
	footer {
		display: flex;
		width: 450px;
	}
}
</style>
