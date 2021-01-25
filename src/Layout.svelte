<main>
	<slot />
</main>

<style>
main {
	pointer-events: auto;
	box-sizing: border-box;
	display: flex;
	flex-basis: auto;
	flex-direction: column;
	min-height: 0px;
	min-width: 0px;
	position: relative;
	z-index: 0;
	width: 100%;
	flex-grow: 1;
	flex-shrink: 1;
	align-items: stretch;
}

@media only screen and (min-width: 1004px) {
	main {
		flex-direction: row;
		justify-content: space-between;
	}
}
</style>
