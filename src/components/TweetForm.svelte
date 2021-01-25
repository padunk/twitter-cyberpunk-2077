<script>
import IoIosImage from "svelte-icons/io/IoIosImage.svelte";
import MdGif from "svelte-icons/md/MdGif.svelte";
import MdInsertEmoticon from "svelte-icons/md/MdInsertEmoticon.svelte";
import GiWorld from "svelte-icons/gi/GiWorld.svelte";
import Avatar from "./Avatar.svelte";
import Button from "./Button.svelte";
</script>

<div class="container">
	<div class="wrapper">
		<div class="avatar-container">
			<Avatar src="/images/avatar_temp2.jpg" alt="woman" size="{40}" />
		</div>
		<div class="form-container">
			<div class="form-input">
				<textarea
					class="tweet-text"
					placeholder="What's going on?"
				></textarea>
				<div class="reply">
					<button class="reply-button">
						<span class="reply-icon">
							<GiWorld />
						</span>
						Everyone can reply
					</button>
				</div>
			</div>
			<div class="cta-container">
				<div>
					<ul>
						<li class="cta-tweet-icon">
							<IoIosImage />
						</li>
						<li class="cta-tweet-icon">
							<MdGif />
						</li>
						<li class="cta-tweet-icon">
							<MdInsertEmoticon />
						</li>
					</ul>
				</div>
				<div class="cta-tweet-wrapper">
					<Button>Tweet</Button>
				</div>
			</div>
		</div>
	</div>
</div>

<style>
.container {
	display: flex;
	position: relative;
	clip-path: polygon(0 0, 100% 0, 100% 100%, 5% 100%, 0 90%);
	z-index: 10;
}

.wrapper {
	display: flex;
	align-items: flex-start;
	padding: 4px 12px;
	width: 100%;
}

.avatar-container {
	flex-grow: auto;
	padding: 0 12px;
}

.form-container {
	flex-grow: 1;
	flex-shrink: 1;
}

.form-input {
	padding-bottom: 12px;
}

.tweet-text {
	width: 100%;
	font-size: 20px;
	background: transparent;
	outline: none;
	border: none;
	font-family: inherit;
	padding-top: 16px;
	line-height: 1;
	color: var(--cyan);
	resize: none;
}

.reply-button {
	display: flex;
	align-items: center;
	background: transparent;
	color: var(--cyan);
	column-gap: 8px;
	font-family: inherit;
	font-weight: 600;
	border: none;
	outline: none;
}

.reply-icon {
	width: 18px;
}

.cta-container {
	display: flex;
	justify-content: space-between;
	align-items: center;
	padding: 8px 0;
	border-top: 1px solid var(--cyan);
}

.cta-tweet-wrapper {
	clip-path: polygon(0 0, 100% 0, 100% 73%, 87% 100%, 0 100%);
	background: var(--primary);
	background: radial-gradient(circle, var(--primary) 0%, var(--cyan) 100%);
	width: 72px;
	height: 38px;
	display: flex;
	justify-content: center;
	align-items: center;
}

ul {
	display: flex;
	align-items: center;
	list-style-type: none;
	column-gap: 12px;
}

.cta-tweet-icon {
	width: 24px;
	color: var(--cyan);
	display: flex;
	align-items: center;
}
</style>
