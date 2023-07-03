<script lang="ts">
	import Slider from '$lib/components/slider.svelte';
	import SiteHeader from '$lib/components/siteHeader.svelte';

	let index = 0;
	// Data
	const discoveryContent = [
		{
			header: 'Discover innovative ways to decorate',
			text: 'We provide unmatched quality, comfort, and style for property owners across the country. Our experts combine form and function in bringing your vision to life. Create a room in your own style with our collection and make your property a reflection of you and what you love.'
		},
		{
			header: 'We are available all across the globe',

			text: "With stores all over the world, it's easy for you to find furniture for your home or place of business. Locally, we’re in most major cities throughout the country. Find the branch nearest you using our store locator. Any questions? Don't hesitate to contact us today."
		},
		{
			header: 'Manufactured with the best materials',

			text: 'Our modern furniture store provide a high level of quality. Our company has invested in advanced technology to ensure that every product is made as perfect and as consistent as possible. With three decades of experience in this industry, we understand what customers want for their home and office.'
		}
	];

	// Actions
	const handleSliderAction = (event: CustomEvent) => {
		index = event.detail.index - 1;
	};
</script>

<div class="wrap">
	<section class="hero" aria-label="Hero">
		<div class="header">
			<SiteHeader />
		</div>
		<div class="slider">
			<Slider quantity={3} on:action={handleSliderAction} />
		</div>
	</section>

	<section aria-labelledby="discover" class="discover">
		<h1 id="discover">{discoveryContent[index].header}</h1>
		<p>{discoveryContent[index].text}</p>
		<a href="/">Shop now</a>
	</section>
</div>

<div class="wrap">
	<section>
		<img src="/images/image-about-dark.jpg" alt="Example - dark" class="example" />
	</section>

	<section aria-labelledby="about" class="about">
		<h2 id="about">About our furniture</h2>

		<p>
			Our multifunctional collection blends design and function to suit your individual taste. Make
			each room unique, or pick a cohesive theme that best express your interests and what inspires
			you. Find the furniture pieces you need, from traditional to contemporary styles or anything
			in between. Product specialists are available to help you create your dream space.
		</p>
	</section>

	<section>
		<img src="/images/image-about-light.jpg" alt="Example - light" class="example" />
	</section>
</div>

<footer>
	Challenge by <a
		href="https://www.frontendmentor.io?ref=challenge"
		target="_blank"
		rel="noopener noreferrer">Frontend Mentor</a
	>. Coded by
	<a href="https://www.frontendmentor.io/profile/sutaC" target="_blank" rel="noopener noreferrer"
		>Your Name Here</a
	>.
</footer>

<!-- Style -->
<style>
	/* Preset */
	@import url('https://fonts.googleapis.com/css2?family=League+Spartan:wght@500;600;700&display=swap');

	:global(*) {
		box-sizing: border-box;
	}

	:global(:root) {
		--clr-mGray: hsl(0, 0%, 63%);
		--clr-black: hsl(0, 0%, 0%);
		--clr-white: hsl(0, 0%, 100%);
		--clr-dGray: hsl(0, 0%, 27%);

		--desktop-breakpoint: 800px;
	}

	:global(html) {
		font-size: 12px;
		font-family: 'League Spartan', sans-serif;
		color: var(--clr-black);
		/* text-wrap: balance; */
	}

	:global(body) {
		margin: 0;
		padding: 0;
		min-height: 100vh;
	}

	/* General */

	img {
		width: 100%;
	}

	p {
		color: var(--clr-mGray);
		line-height: 1.25em;
	}

	/* Main */

	section.hero {
		position: relative;
	}
	section.hero > .header {
		position: absolute;
		z-index: 1;
		width: 100%;
	}

	section.discover,
	section.about {
		padding: 4rem 2rem;
	}

	section.discover > h1 {
		font-size: 3.1rem;
		margin: 0;
	}
	section.discover > a {
		color: var(--clr-black);
		font-weight: bolder;
		text-decoration: none;
		text-transform: uppercase;
		letter-spacing: 1em;
		font-size: 1.1rem;
	}
	section.discover > a::after {
		content: url('/images/icon-arrow.svg');
		margin-left: 1em;
	}
	section.discover > a:hover,
	section.discover > a:focus,
	section.discover > a:active {
		color: var(--clr-dGray);
	}

	section.about > h2 {
		font-size: 1rem;
		text-transform: uppercase;
		letter-spacing: 0.5em;
		margin: 0;
	}

	/* Footer */

	footer {
		position: fixed;
		left: 0;
		bottom: 0;
		text-align: center;
		width: 100vw;
		font-size: 0.7rem;
	}

	/* Desktop view */

	@media (width >= 1000px) {
		.wrap {
			display: flex;
			justify-content: center;
			align-items: start;
		}

		.wrap:nth-child(2) {
			translate: 0 -0.2rem;
			justify-content: space-between;
		}

		section.discover,
		section.about {
			display: flex;
			justify-content: center;
			align-items: color;
			flex-direction: column;
			min-width: 30%;
		}

		section.discover {
			padding-top: 12.5%;
		}
	}
</style>
