<script lang="ts">
	const journeySteps = [
		{
			stage: "Connect",
			title: "Meet",
			description: "Meet people from eight countries."
		},
		{
			stage: "Explore",
			title: "Discover",
			description: "Discover digital tools and new perspectives."
		},
		{
			stage: "Question",
			title: "Discuss",
			description: "Discuss AI ethics and online responsibility."
		},
		{
			stage: "Create",
			title: "Build",
			description: "Transform ideas into practical activities."
		},
		{
			stage: "Share",
			title: "Bring home",
			description: "Bring the knowledge back to local communities."
		}
	];
</script>

<section class="journey" id="journey">
	<div class="journey__inner">
		<div class="section-label">
			<span></span>
			<p>04 / The shared journey</p>
		</div>

		<h2>
			From connection to
			<em>creation.</em>
		</h2>

		<div class="journey__visual" aria-hidden="true">
			<svg viewBox="0 0 1200 190" fill="none" preserveAspectRatio="none">
				<path
					d="
						M20 128
						C110 178 205 86 310 98
						C405 110 420 160 500 142
						C590 122 650 52 735 72
						C815 92 825 130 910 105
						C1000 78 1080 48 1180 68
					"
				/>

				<circle cx="20" cy="128" r="5"></circle>
				<circle cx="310" cy="98" r="5"></circle>
				<circle cx="500" cy="142" r="5"></circle>
				<circle cx="735" cy="72" r="5"></circle>
				<circle cx="1180" cy="68" r="5"></circle>
			</svg>
		</div>

		<div class="journey__steps">
			{#each journeySteps as step, index}
				<article class="journey-step">
					<p class="journey-step__label">
						<span>{String(index + 1).padStart(2, "0")}</span>
						{step.stage}
					</p>

					<h3>{step.title}</h3>
					<p class="journey-step__description">{step.description}</p>
				</article>
			{/each}
		</div>
	</div>
</section>

<style>
	.journey {
		--cream: #f3f0e7;
		--forest: #123f37;
		--aqua: #48c8cb;
		--blue: #82bcc5;
		--grey: #5b6561;

		position: relative;
		padding: clamp(100px, 12vw, 170px) 32px;
		overflow: hidden;
		background: var(--cream);
	}

	.journey__inner {
		width: min(1420px, 100%);
		margin-inline: auto;
	}

	.section-label {
		display: flex;
		align-items: center;
		gap: 14px;
		margin-bottom: 34px;
	}

	.section-label > span {
		width: 34px;
		height: 1px;
		background: rgba(18, 63, 55, 0.35);
	}

	.section-label p {
		margin: 0;
		color: #587068;
		font-family: var(--font-mono);
		font-size: 0.72rem;
		letter-spacing: 0.18em;
		text-transform: uppercase;
	}

	h2 {
		max-width: 950px;
		margin: 0;
		color: var(--forest);
		font-family: var(--font-display);
		font-size: clamp(3.5rem, 5.5vw, 6rem);
		font-weight: 400;
		letter-spacing: -0.05em;
		line-height: 0.95;
	}

	h2 em {
		color: var(--blue);
		font-weight: 400;
	}

	.journey__visual {
		width: 100%;
		margin-top: clamp(105px, 10vw, 155px);
	}

	svg {
		display: block;
		width: 100%;
		height: 190px;
		overflow: visible;
	}

	path {
		stroke: var(--aqua);
		stroke-width: 2;
		vector-effect: non-scaling-stroke;
	}

	circle {
		fill: var(--aqua);
		stroke: var(--cream);
		stroke-width: 7;
		vector-effect: non-scaling-stroke;
	}

	.journey__steps {
		display: grid;
		grid-template-columns: repeat(5, minmax(0, 1fr));
		gap: clamp(24px, 3vw, 52px);
		margin-top: 42px;
	}

	.journey-step {
		max-width: 235px;
	}

	.journey-step__label {
		display: flex;
		gap: 10px;
		margin: 0;
		color: var(--aqua);
		font-family: var(--font-mono);
		font-size: 0.72rem;
		font-weight: 500;
		letter-spacing: 0.08em;
		text-transform: uppercase;
	}

	.journey-step__label span {
		color: var(--aqua);
	}

	.journey-step h3 {
		margin: 14px 0 0;
		color: var(--forest);
		font-family: var(--font-body);
		font-size: 1.15rem;
		font-weight: 500;
		letter-spacing: 0.02em;
	}

	.journey-step__description {
		margin: 12px 0 0;
		color: var(--grey);
		font-size: 0.92rem;
		line-height: 1.55;
	}

	@media (max-width: 850px) {
		.journey__visual {
			display: none;
		}

		.journey__steps {
			position: relative;
			grid-template-columns: 1fr;
			gap: 48px;
			margin-top: 75px;
			padding-left: 48px;
		}

		.journey__steps::before {
			position: absolute;
			top: 8px;
			bottom: 8px;
			left: 12px;
			border-left: 2px solid var(--aqua);
			content: "";
		}

		.journey-step {
			position: relative;
			max-width: 420px;
		}

		.journey-step::before {
			position: absolute;
			top: 2px;
			left: -42px;
			width: 12px;
			height: 12px;
			border: 5px solid var(--cream);
			border-radius: 50%;
			background: var(--aqua);
			box-sizing: content-box;
			content: "";
		}

		.journey-step h3 {
			font-size: 1.2rem;
		}

		.journey-step__description {
			font-size: 1rem;
		}
	}

	@media (max-width: 560px) {
		.journey {
			padding-inline: 20px;
		}

		h2 {
			font-size: clamp(3.2rem, 15vw, 4.5rem);
		}

		h2 em {
			display: block;
		}
	}
</style>
