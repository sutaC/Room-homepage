<script lang="ts">
	import Slider from '$lib/components/slider.svelte';
	import SiteHeader from '$lib/components/siteHeader.svelte';
</script>

<section class="hero" aria-label="Hero">
	<header>
		<SiteHeader />
	</header>
	<div class="slider">
		<Slider />
	</div>
</section>

<section aria-labelledby="discover">
	<h1 id="discover">Discover innovative ways to decorate</h1>
	<p>
		We provide unmatched quality, comfort, and style for property owners across the country. Our
		experts combine form and function in bringing your vision to life. Create a room in your own
		style with our collection and make your property a reflection of you and what you love.
	</p>
	<a href="/">Shop now</a>
</section>

<img src="/images/image-about-dark.jpg" alt="Example - dark" class="example" />

<section aria-labelledby="about">
	<h2 id="about">About our furniture</h2>

	<p>
		Our multifunctional collection blends design and function to suit your individual taste. Make
		each room unique, or pick a cohesive theme that best express your interests and what inspires
		you. Find the furniture pieces you need, from traditional to contemporary styles or anything in
		between. Product specialists are available to help you create your dream space.
	</p>
</section>

<img src="/images/image-about-light.jpg" alt="Example - light" class="example" />

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
</style>
