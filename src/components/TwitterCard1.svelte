<script>
import GiRapidshareArrow from "svelte-icons/gi/GiRapidshareArrow.svelte";
import IoIosMore from "svelte-icons/io/IoIosMore.svelte";
import GoComment from "svelte-icons/go/GoComment.svelte";
import GiTechnoHeart from "svelte-icons/gi/GiTechnoHeart.svelte";
import MdRepeat from "svelte-icons/md/MdRepeat.svelte";
import Avatar from "./Avatar.svelte";
import Icon from "./Icons/Icon.svelte";
let random = Math.floor(Math.random() * 5 + 1);
</script>

<article>
	<div class="container">
		<div class="header-wrapper">
			<Avatar
				src="/images/avatar_temp{random}.jpg"
				alt="anna"
				size="{45}"
			/>
			<div class="header">
				<div>
					<p>
						<span class="handle-text-normal">V</span>
						<span class="handle-text-dark">@v</span>
						<span class="handle-text-dark">&dotsquare;</span>
						<span class="handle-text-dark">66s</span>
					</p>
				</div>
				<div>
					<Icon size="{20}">
						<IoIosMore />
					</Icon>
				</div>
			</div>
		</div>
		<div class="body-wrapper">
			<div class="body-text">
				<p>
					It wasn't until after college, when I went to Chicago to
					work as a community organizer for a group of Christian
					churches, that I confronted my own spiritual dilemma.
				</p>
				<div>images</div>
			</div>
		</div>
		<div class="footer-wrapper">
			<ul>
				<li class="comment">
					<Icon size="{20}">
						<GoComment />
					</Icon>
					<span>99.1 K</span>
				</li>
				<li class="retweet">
					<Icon size="{20}">
						<MdRepeat />
					</Icon>
					<span>99.1 K</span>
				</li>
				<li class="like">
					<Icon size="{20}">
						<GiTechnoHeart />
					</Icon>
					<span>99.1 K</span>
				</li>
				<li class="other">
					<Icon size="{20}">
						<GiRapidshareArrow />
					</Icon>
				</li>
			</ul>
		</div>
	</div>
</article>

<style>
article {
	display: flex;
	border-bottom: 1px solid var(--cyan);
}

.container {
	padding: 12px;
}

.header-wrapper {
	display: flex;
}

.header {
	display: flex;
	justify-content: space-between;
	align-items: flex-end;
	width: 100%;
	padding: 0 12px;
}

.handle-text-normal {
	color: var(--yellow);
}

.handle-text-dark {
	font-size: 14px;
	color: var(--red-dark-4);
}

.body-wrapper {
	display: flex;
}

.body-text {
	padding: 8px;
}

.footer-wrapper {
	display: flex;
}

ul {
	display: flex;
	align-items: center;
	justify-content: space-around;
	width: 100%;
	font-size: 12px;
	color: var(--red-dark-4);
}

li {
	display: flex;
	align-items: center;
	column-gap: 4px;
	padding: 4px;
	clip-path: polygon(0 0, 90% 0, 100% 15%, 100% 100%, 0 100%);
	cursor: pointer;
	transition-property: color, background-color;
	transition-duration: 200ms;
}

li:hover {
	color: var(--cyan);
	background: var(--secondary);
}

.like:hover {
	color: var(--magenta);
	background: var(--secondary);
}

.retweet:hover {
	color: var(--orange);
	background: var(--secondary);
}
</style>
