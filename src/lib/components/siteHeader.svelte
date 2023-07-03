<header>
	<button class="hamburger"><img src="/images/icon-hamburger.svg" alt="Open navigation" /></button>
	<nav>
		<button>
			<img src="/images/icon-close.svg" alt="Close" />
		</button>
		<a href="/">Home</a>
		<a href="/">Shop</a>
		<a href="/">About</a>
		<a href="/">Contact</a>
	</nav>
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

	.hamburger {
		position: absolute;

		left: 1.5rem;
		top: 50%;
		translate: 0 -50%;

		background-color: transparent;
		border: none;
	}
</style>
