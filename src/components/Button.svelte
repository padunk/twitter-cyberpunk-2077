<button>
	<slot />
</button>

<style>
button {
	clip-path: polygon(0 0, 100% 0, 100% 73%, 87% 100%, 0 100%);
	padding: 6px 10px;
	background: var(--yellow);
	color: var(--primary);
	border: none;
	outline: none;
	font-size: 16px;
	font-family: inherit;
	font-weight: 700;
	border-radius: 0;
	width: 70px;
	height: 36px;
	cursor: pointer;
}
</style>
