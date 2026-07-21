<script lang="ts">
	let menuOpen = $state(false);

	function closeMenu() {
		menuOpen = false;
	}
</script>

<header class="navigation">
	<div class="navigation__inner">
		<a class="logo" href="/" onclick={closeMenu}>
			DigiPack
			<span>Connected · Stara Zagora</span>
		</a>

		<button
			class="menu-button"
			type="button"
			aria-label="Toggle navigation"
			aria-expanded={menuOpen}
			onclick={() => (menuOpen = !menuOpen)}
		>
			<span></span>
			<span></span>
		</button>

		<nav class:nav-open={menuOpen} aria-label="Main navigation">
			<a href="#about" onclick={closeMenu}>About</a>
			<a href="#topics" onclick={closeMenu}>Topics</a>
			<a href="#activities" onclick={closeMenu}>Activities</a>
			<a href="#gallery" onclick={closeMenu}>Gallery</a>
		</nav>
	</div>
</header>

<style>
	.navigation {
		--cream: #f3f0e7;
		--forest: #123f37;
		--aqua: #48c8cb;

		position: sticky;
		z-index: 100;
		top: 0;
		width: 100%;
		border-bottom: 1px solid rgba(18, 63, 55, 0.12);
		background: rgba(243, 240, 231, 0.92);
		backdrop-filter: blur(16px);
		-webkit-backdrop-filter: blur(16px);
	}

	.navigation__inner {
		display: flex;
		align-items: center;
		justify-content: space-between;
		width: min(1420px, calc(100% - 64px));
		min-height: 82px;
		margin-inline: auto;
	}

	.logo {
		color: var(--forest);
		font-family: var(--font-display);
		font-size: 1.6rem;
		line-height: 1;
		text-decoration: none;
	}

	.logo span {
		margin-left: 12px;
		font-family: var(--font-mono);
		font-size: 0.62rem;
		letter-spacing: 0.17em;
		text-transform: uppercase;
	}

	nav {
		display: flex;
		align-items: center;
		gap: 40px;
	}

	nav a {
		position: relative;
		padding-block: 8px;
		color: var(--forest);
		font-family: var(--font-mono);
		font-size: 0.68rem;
		letter-spacing: 0.17em;
		text-decoration: none;
		text-transform: uppercase;
	}

	nav a::after {
		position: absolute;
		right: 0;
		bottom: 0;
		left: 0;
		height: 1px;
		background: var(--aqua);
		content: "";
		transform: scaleX(0);
		transform-origin: right;
		transition: transform 200ms ease;
	}

	nav a:hover::after {
		transform: scaleX(1);
		transform-origin: left;
	}

	.menu-button {
		display: none;
		width: 42px;
		height: 42px;
		padding: 0;
		border: 0;
		background: transparent;
		cursor: pointer;
	}

	.menu-button span {
		display: block;
		width: 24px;
		height: 1px;
		margin: 6px auto;
		background: var(--forest);
	}

	@media (max-width: 800px) {
		.navigation__inner {
			position: relative;
			width: calc(100% - 40px);
			min-height: 72px;
		}

		.logo span {
			display: none;
		}

		.menu-button {
			display: block;
		}

		nav {
			position: absolute;
			top: 72px;
			right: -20px;
			left: -20px;
			display: flex;
			align-items: flex-start;
			flex-direction: column;
			gap: 0;
			padding: 12px 20px 24px;
			border-bottom: 1px solid rgba(18, 63, 55, 0.12);
			background: var(--cream);
			opacity: 0;
			pointer-events: none;
			transform: translateY(-10px);
			transition:
				opacity 180ms ease,
				transform 180ms ease;
		}

		nav.nav-open {
			opacity: 1;
			pointer-events: auto;
			transform: translateY(0);
		}

		nav a {
			width: 100%;
			padding: 16px 0;
			border-bottom: 1px solid rgba(18, 63, 55, 0.1);
		}
	}
</style>
