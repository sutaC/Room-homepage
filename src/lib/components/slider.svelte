<script lang="ts">
	import { createEventDispatcher } from 'svelte';
	import { prevent_default } from 'svelte/internal';

	export let quantity = 1;

	$: devidceWidth = 0;
	$: device = devidceWidth < 1000 ? 'mobile' : 'desktop';
	let index = 1;

	// Actions
	const dispatch = createEventDispatcher();

	const moveLeft = () => {
		if (index > 1) {
			index--;
			dispatch('action', {
				index
			});
		}
	};

	const moveRight = () => {
		if (index < quantity) {
			index++;
			dispatch('action', {
				index
			});
		}
	};

	const handleKeyPress = (event: KeyboardEvent) => {
		switch (event.key) {
			case 'ArrowLeft':
				event.preventDefault();
				moveLeft();
				break;

			case 'ArrowRight':
				event.preventDefault();
				moveRight();
				break;
		}
	};
</script>

<svelte:window bind:innerWidth={devidceWidth} on:keydown={handleKeyPress} />

<div class="slider">
	<img src="/images/{device}-image-hero-{index}.jpg" alt="Main example" />
	<div class="controls">
		<button on:click={() => moveLeft()}>
			<img src="/images/icon-angle-left.svg" alt="Show on left" />
		</button>
		<button on:click={() => moveRight()}>
			<img src="/images/icon-angle-right.svg" alt="Show on right" />
		</button>
	</div>
</div>

<style>
	.slider {
		position: relative;
	}

	.slider > img {
		width: 100%;
	}

	.controls {
		position: absolute;
		bottom: 0.2rem;
		right: 0;

		width: clamp(10vw, 30%, 10rem);

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
		aspect-ratio: 1;
	}
	.controls > button > img {
		width: 25%;
	}

	/* States */

	.controls > button:hover,
	.controls > button:focus,
	.controls > button:active {
		background-color: var(--clr-dGray);
		cursor: pointer;
	}

	/* Desktop view */

	@media (width >= 1000px) {
		.slider > img {
			width: 60.25vw;
		}

		.controls {
			translate: 100% 0;
		}
	}
</style>
