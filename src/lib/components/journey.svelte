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

	const digitalTools = [
		{
			name: "ChatGPT",
			shortName: "GPT",
			className: "tool--chatgpt"
		},
		{
			name: "Canva",
			shortName: "C",
			className: "tool--canva"
		},
		{
			name: "NotebookLM",
			shortName: "NLM",
			className: "tool--notebook"
		},
		{
			name: "Claude",
			shortName: "AI",
			className: "tool--claude"
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
			<div class="digital-tools">
				{#each digitalTools as tool}
					<div class={`digital-tool ${tool.className}`}>
						<div class="digital-tool__icon">
							{tool.shortName}
						</div>

						<span>{tool.name}</span>
					</div>
				{/each}
			</div>

			<svg
				viewBox="0 0 1200 190"
				fill="none"
				preserveAspectRatio="none"
			>
				<path
					class="river-path"
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
				<article
					class="journey-step"
					style={`--step-index: ${index}`}
				>
					<p class="journey-step__label">
						<span>
							{String(index + 1).padStart(2, "0")}
						</span>

						{step.stage}
					</p>

					<h3>{step.title}</h3>

					<p class="journey-step__description">
						{step.description}
					</p>
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
		animation: reveal-up 700ms ease both;
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
		animation: reveal-up 800ms ease 100ms both;
	}

	h2 em {
		color: var(--blue);
		font-weight: 400;
	}

	.journey__visual {
		position: relative;
		width: 100%;
		margin-top: clamp(105px, 10vw, 155px);
	}

	.journey__visual svg {
		display: block;
		width: 100%;
		height: 190px;
		overflow: visible;
	}

	.river-path {
		stroke: var(--aqua);
		stroke-width: 2;
		stroke-dasharray: 1600;
		stroke-dashoffset: 1600;
		vector-effect: non-scaling-stroke;
		animation: draw-river 2.5s ease 300ms forwards;
	}

	.journey__visual circle {
		transform: scale(0);
		transform-box: fill-box;
		transform-origin: center;
		fill: var(--aqua);
		stroke: var(--cream);
		stroke-width: 7;
		vector-effect: non-scaling-stroke;
		animation: show-dot 500ms ease forwards;
	}

	.journey__visual circle:nth-of-type(1) {
		animation-delay: 500ms;
	}

	.journey__visual circle:nth-of-type(2) {
		animation-delay: 850ms;
	}

	.journey__visual circle:nth-of-type(3) {
		animation-delay: 1.15s;
	}

	.journey__visual circle:nth-of-type(4) {
		animation-delay: 1.45s;
	}

	.journey__visual circle:nth-of-type(5) {
		animation-delay: 1.8s;
	}

	.digital-tools {
		position: absolute;
		z-index: 2;
		inset: 0;
		pointer-events: none;
	}

	.digital-tool {
		position: absolute;
		display: flex;
		align-items: center;
		flex-direction: column;
		gap: 8px;
		opacity: 0;
		animation:
			show-tool 700ms ease forwards,
			float-tool 5s ease-in-out infinite;
	}

	.digital-tool__icon {
		display: grid;
		width: 56px;
		height: 56px;
		border: 1px solid rgba(18, 63, 55, 0.14);
		border-radius: 17px;
		background: rgba(255, 255, 255, 0.85);
		box-shadow: 0 12px 30px rgba(18, 63, 55, 0.1);
		color: var(--forest);
		font-family: var(--font-mono);
		font-size: 0.75rem;
		font-weight: 700;
		letter-spacing: -0.02em;
		place-items: center;
		backdrop-filter: blur(8px);
	}

	.digital-tool > span {
		padding: 4px 8px;
		border-radius: 999px;
		background: rgba(243, 240, 231, 0.9);
		color: rgba(18, 63, 55, 0.72);
		font-family: var(--font-mono);
		font-size: 0.56rem;
		letter-spacing: 0.08em;
		text-transform: uppercase;
		white-space: nowrap;
	}

	.tool--chatgpt {
		top: 42px;
		left: 9%;
		transform: rotate(-6deg);
		animation-delay: 500ms, 1.2s;
	}

	.tool--canva {
		top: -34px;
		left: 31%;
		transform: rotate(5deg);
		animation-delay: 750ms, 1.45s;
	}

	.tool--notebook {
		top: 50px;
		left: 57%;
		transform: rotate(-4deg);
		animation-delay: 1s, 1.7s;
	}

	.tool--claude {
		top: -42px;
		left: 82%;
		transform: rotate(7deg);
		animation-delay: 1.25s, 1.95s;
	}

	.tool--chatgpt .digital-tool__icon {
		border-radius: 50%;
	}

	.tool--canva .digital-tool__icon {
		border-radius: 20px 10px 20px 10px;
	}

	.tool--notebook .digital-tool__icon {
		border-radius: 10px;
	}

	.tool--claude .digital-tool__icon {
		border-radius: 50% 50% 45% 55%;
	}

	.journey__steps {
		display: grid;
		grid-template-columns: repeat(5, minmax(0, 1fr));
		gap: clamp(24px, 3vw, 52px);
		margin-top: 42px;
	}

	.journey-step {
		max-width: 235px;
		opacity: 0;
		animation: reveal-up 700ms ease forwards;
		animation-delay: calc(700ms + var(--step-index) * 120ms);
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

	@keyframes draw-river {
		from {
			stroke-dashoffset: 1600;
		}

		to {
			stroke-dashoffset: 0;
		}
	}

	@keyframes show-dot {
		from {
			transform: scale(0);
			opacity: 0;
		}

		to {
			transform: scale(1);
			opacity: 1;
		}
	}

	@keyframes show-tool {
		from {
			translate: 0 18px;
			opacity: 0;
		}

		to {
			translate: 0 0;
			opacity: 1;
		}
	}

	@keyframes float-tool {
		0%,
		100% {
			margin-top: 0;
		}

		50% {
			margin-top: -10px;
		}
	}

	@keyframes reveal-up {
		from {
			transform: translateY(25px);
			opacity: 0;
		}

		to {
			transform: translateY(0);
			opacity: 1;
		}
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

	@media (prefers-reduced-motion: reduce) {
		.section-label,
		h2,
		.river-path,
		.journey__visual circle,
		.digital-tool,
		.journey-step {
			animation: none;
			transform: none;
			translate: none;
			opacity: 1;
		}

		.river-path {
			stroke-dashoffset: 0;
		}

		.journey__visual circle {
			transform: scale(1);
		}
	}
</style>
