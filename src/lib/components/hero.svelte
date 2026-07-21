<section class="hero">
	<div class="hero__art" aria-hidden="true"></div>
	<div class="hero__overlay" aria-hidden="true"></div>


	<div class="hero__content">
		<p class="eyebrow">Erasmus+ / Youth work / 2026</p>

		<h1>
			DigiPack of Tools
			<em>for Youth Workers</em>
		</h1>

		<p class="introduction">
			Exploring digital tools, AI and cybersecurity—while staying
			connected to people, place and nature.
		</p>

		<div class="details">
			<div class="detail">
				<span>Dates</span>
				<strong>15–23 July 2026</strong>
			</div>

			<div class="detail">
				<span>Location</span>
				<strong>Stara Zagora, BG</strong>
			</div>
		</div>

		<div class="actions">
			<a class="primary-button" href="#about">
				Explore the project
				<span aria-hidden="true">●</span>
			</a>

			<a class="text-link" href="#journey">
				Follow the digital river →
			</a>
		</div>
	</div>

	<svg
		class="river-line"
		viewBox="0 0 1600 700"
		fill="none"
		preserveAspectRatio="none"
		aria-hidden="true"
	>
		<path
			d="M-60 690C270 650 480 560 720 420C970 275 1250 130 1660 -20"
		/>
	</svg>
</section>

<style>
	:global(*) {
		box-sizing: border-box;
	}

	:global(body) {
		margin: 0;
		background: #f3f0e7;
		color: #123f37;
		font-family: Arial, sans-serif;
	}

	.hero {
		--cream: #f3f0e7;
		--forest: #123f37;
		--sage: #668675;
		--aqua: #48c8cb;

		position: relative;
		min-height: 100svh;
		overflow: hidden;
		background: var(--cream);
	}

	.hero__art {
		position: absolute;
		inset: 0 0 0 39%;
		background:
			linear-gradient(90deg, var(--cream) 0%, transparent 30%),
			linear-gradient(0deg, rgba(18, 63, 55, 0.16), transparent 55%),
			url("/images/artwork/digipack-stara-zagora.png") center / cover no-repeat;
	}

	.hero__overlay {
		position: absolute;
		inset: 0;
		background: linear-gradient(
			90deg,
			var(--cream) 0%,
			rgba(243, 240, 231, 0.96) 23%,
			rgba(243, 240, 231, 0.55) 48%,
			transparent 70%
		);
	}

	.hero__content {
		position: relative;
		z-index: 2;
		width: min(1420px, calc(100% - 64px));
		margin-inline: auto;
		padding-top: clamp(150px, 19vh, 230px);
	}

	.eyebrow {
		margin: 0 0 20px;
		font-family: monospace;
		font-size: 0.75rem;
		letter-spacing: 0.16em;
		text-transform: uppercase;
	}

	h1 {
		max-width: 730px;
		margin: 0;
		font-family: Georgia, serif;
		font-size: clamp(4rem, 6.2vw, 7rem);
		font-weight: 400;
		letter-spacing: -0.055em;
		line-height: 0.86;
	}

	h1 em {
		display: block;
		margin-top: 12px;
		color: var(--sage);
		font-weight: 400;
	}

	.introduction {
		max-width: 590px;
		margin: 42px 0 0;
		color: #53615d;
		font-size: 1.1rem;
		line-height: 1.65;
	}

	.details {
		display: flex;
		gap: 56px;
		margin-top: 34px;
		padding-left: 20px;
		border-left: 2px solid var(--aqua);
	}

	.detail {
		display: flex;
		flex-direction: column;
		gap: 5px;
	}

	.detail span {
		font-family: monospace;
		font-size: 0.67rem;
		letter-spacing: 0.18em;
		text-transform: uppercase;
	}

	.detail strong {
		font-family: Georgia, serif;
		font-size: 1.35rem;
		font-weight: 400;
	}

	.actions {
		display: flex;
		align-items: center;
		gap: 30px;
		margin-top: 38px;
	}

	.primary-button {
		display: flex;
		align-items: center;
		gap: 18px;
		padding: 17px 26px;
		border-radius: 999px;
		background: var(--forest);
		color: white;
		text-decoration: none;
	}

	.primary-button span {
		color: var(--aqua);
		font-size: 0.75rem;
	}

	.text-link {
		padding-bottom: 5px;
		border-bottom: 1px solid rgba(18, 63, 55, 0.3);
		color: var(--forest);
		font-family: monospace;
		font-size: 0.72rem;
		letter-spacing: 0.13em;
		text-decoration: none;
		text-transform: uppercase;
	}

	.river-line {
		position: absolute;
		z-index: 1;
		inset: auto 0 0;
		width: 100%;
		height: 88%;
		pointer-events: none;
	}

	.river-line path {
		stroke: var(--aqua);
		stroke-width: 1.5;
		vector-effect: non-scaling-stroke;
	}

	@media (max-width: 800px) {
		.hero {
			min-height: calc(100svh - 72px);
			padding-bottom: 80px;
			background: var(--cream);
		}

		.hero__art {
			inset: 0;
			width: 100%;
			height: auto;
			opacity: 1;
			background:
				url("/images/artwork/digipack-stara-zagora.png")
					62% center / cover no-repeat;
		}

		.hero__overlay {
			inset: 0;
			background: linear-gradient(
				180deg,
				rgba(243, 240, 231, 0.12) 0%,
				rgba(243, 240, 231, 0.42) 28%,
				rgba(243, 240, 231, 0.72) 58%,
				rgba(243, 240, 231, 0.86) 100%
			);
		}

		.hero__content {
				width: calc(100% - 40px);
				padding-top: 100px;
				padding-bottom: 40px;
			}

		.eyebrow {
			margin-bottom: 16px;
			font-size: 0.67rem;
		}

		h1 {
			max-width: 100%;
			font-size: clamp(3.3rem, 14vw, 4.6rem);
			line-height: 0.88;
		}

		h1 em {
			margin-top: 8px;
		}

		.introduction {
			margin-top: 32px;
			font-size: 1rem;
			line-height: 1.6;
		}

		.details,
		.actions {
			align-items: flex-start;
			flex-direction: column;
			gap: 22px;
		}

		.river-line {
			height: 75%;
			opacity: 0.8;
		}
}
</style>
