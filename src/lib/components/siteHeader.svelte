<script lang="ts">
	import { slide } from 'svelte/transition';

	let navActive = false;
</script>

<header>
	<button class="hamburger" on:click={() => (navActive = true)}
		><img src="/images/icon-hamburger.svg" alt="Open navigation" /></button
	>

	<nav class:navActive>
		<button on:click={() => (navActive = false)} class="close">
			<img src="/images/icon-close.svg" alt="Close" />
		</button>
		<a href="/">Home</a>
		<a href="/">Shop</a>
		<a href="/">About</a>
		<a href="/">Contact</a>
	</nav>
	<div class="backdrop" />
	<img src="/images/logo.svg" alt="Logo" />
</header>

<style>
	header {
		position: relative;

		display: flex;
		justify-content: center;
		align-items: center;
		width: 100%;
		padding: 3rem 2rem;
	}

	nav {
		display: none;
	}

	.navActive {
		display: block;
		position: fixed;
		top: 0;
		left: 0;

		padding: 3.5rem;
		width: 100%;
		background-color: var(--clr-white);

		display: flex;
		justify-content: center;
		align-items: center;
		gap: 10%;

		z-index: 100;
	}
	.navActive + .backdrop {
		width: 100vw;
		height: 100vh;
		position: fixed;
		inset: 0;
		background-color: var(--clr-black);
		opacity: 0.4;
	}

	nav > a {
		text-transform: lowercase;
		text-decoration: none;
		color: var(--clr-black);
		font-weight: bolder;
		font-size: 1.25rem;
	}

	button {
		background-color: transparent;
		border: none;
	}

	button.hamburger {
		position: absolute;

		left: 1.5rem;
		top: 50%;
		translate: 0 -50%;
	}

	button.close {
		margin-right: 2rem;
	}
</style>
