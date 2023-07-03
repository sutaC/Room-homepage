<div class="slider">
	<img src="/images/mobile-image-hero-1.jpg" alt="Main example" />
	<div class="controls">
		<button class="left">
			<img src="/images/icon-angle-left.svg" alt="Show on left" />
		</button>
		<button class="right">
			<img src="/images/icon-angle-right.svg" alt="Show on right" />
		</button>
	</div>
</div>

<style>
	.slider {
		position: relative;
	}

	.controls {
		position: absolute;
		bottom: 0.2rem;
		right: 0;

		width: 33%;

		aspect-ratio: 2 / 1;
		display: flex;
		justify-content: space-evenly;
		align-items: center;

		background-color: var(--clr-black);
	}

	.controls > button {
		background-color: transparent;
		border: none;
		padding: 0;
		flex: 1;
	}
	.controls > button > img {
		width: 25%;
	}
</style>
