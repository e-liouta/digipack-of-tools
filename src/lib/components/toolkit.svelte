<script lang="ts">
	const topics = [
		{
			title: "Digital Tools",
			description:
				"Creative platforms and practical methods that make youth work more engaging, collaborative and accessible.",
			keywords: ["Create", "Collaborate", "Engage"],
			image: "/images/artwork/digipack-digital-tools.png"
		},
		{
			title: "AI & Ethics",
			description:
				"Exploring artificial intelligence with curiosity, critical thinking and care for the people it affects.",
			keywords: ["Question", "Reflect", "Use responsibly"],
			image: "/images/artwork/digipack-ai-ethics.png"
		},
		{
			title: "Cybersecurity",
			description:
				"Recognising online risks, protecting personal information and creating safer digital spaces for young people.",
			keywords: ["Recognise", "Protect", "Prevent"],
			image: "/images/artwork/digipack-cybersecurity.png"
		}
	];
</script>

<section class="topics" id="topics">
	<div class="topics__inner">
		<div class="section-label">
			<span></span>
			<p>02 / Our digital toolkit</p>
		</div>

		<h2>
			Tools for navigating the
			<em>digital world.</em>
		</h2>

		<div class="topics__grid">
			{#each topics as topic}
				<article class="topic-card">
					<div
						class="topic-card__image"
						style:background-image={`url("${topic.image}")`}
					>
					</div>

					<div class="topic-card__content">
						<h3>{topic.title}</h3>
						<p>{topic.description}</p>

						<ul aria-label={`${topic.title} keywords`}>
							{#each topic.keywords as keyword}
								<li>{keyword}</li>
							{/each}
						</ul>
					</div>
				</article>
			{/each}
		</div>
	</div>
</section>

<style>
	.topics {
		--forest: #103d35;
		--forest-dark: #0b332d;
		--cream: #f3f0e7;
		--sage: #9bad92;
		--aqua: #48c8cb;

		position: relative;
		padding: clamp(100px, 12vw, 170px) 32px;
		overflow: hidden;
		background-color: var(--forest);
		background-image:
			linear-gradient(rgba(72, 200, 203, 0.035) 1px, transparent 1px),
			linear-gradient(90deg, rgba(72, 200, 203, 0.035) 1px, transparent 1px);
		background-size: 56px 56px;
	}

	.topics__inner {
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
		background: rgba(243, 240, 231, 0.3);
	}

	.section-label p {
		margin: 0;
		color: var(--sage);
		font-family: monospace;
		font-size: 0.72rem;
		letter-spacing: 0.18em;
		text-transform: uppercase;
	}

	h2 {
		max-width: 900px;
		margin: 0;
		color: var(--cream);
		font-family: Georgia, serif;
		font-size: clamp(3.5rem, 5.5vw, 6rem);
		font-weight: 400;
		letter-spacing: -0.05em;
		line-height: 0.95;
	}

	h2 em {
		color: var(--aqua);
		font-weight: 400;
	}

	.topics__grid {
		display: grid;
		grid-template-columns: repeat(3, minmax(0, 1fr));
		gap: 28px;
		margin-top: clamp(70px, 8vw, 110px);
	}

	.topic-card {
		min-height: 570px;
		overflow: hidden;
		border: 1px solid rgba(72, 200, 203, 0.22);
		border-radius: 7px;
		background: rgba(8, 46, 40, 0.45);
		transition:
			transform 250ms ease,
			border-color 250ms ease;
	}

	.topic-card:hover {
		transform: translateY(-8px);
		border-color: rgba(72, 200, 203, 0.75);
	}

	.topic-card__image {
		position: relative;
		height: 300px;
		background-color: #87aaa0;
		background-position: center;
		background-size: cover;
	}

	.topic-card__content {
		display: flex;
		flex-direction: column;
		min-height: 270px;
		padding: 14px 28px 28px;
	}

	h3 {
		margin: 0;
		color: var(--cream);
		font-family: Georgia, serif;
		font-size: 2rem;
		font-weight: 400;
	}

	.topic-card__content > p {
		margin: 20px 0 0;
		color: var(--sage);
		font-size: 0.97rem;
		line-height: 1.6;
	}

	ul {
		display: flex;
		flex-wrap: wrap;
		gap: 10px 24px;
		margin: auto 0 0;
		padding: 30px 0 0;
		list-style: none;
	}

	li {
		color: var(--aqua);
		font-family: monospace;
		font-size: 0.65rem;
		letter-spacing: 0.15em;
		text-transform: uppercase;
	}

	li::before {
		margin-right: 10px;
		content: "·";
	}

	@media (max-width: 1000px) {
		.topics__grid {
			grid-template-columns: 1fr;
		}

		.topic-card {
			display: grid;
			grid-template-columns: minmax(280px, 0.9fr) 1.1fr;
			min-height: 380px;
		}

		.topic-card__image {
			height: 100%;
		}

		.topic-card__content {
			min-height: 380px;
			padding: 45px 35px 35px;
		}
	}

	@media (max-width: 650px) {
		.topics {
			padding-inline: 20px;
		}

		h2 {
			font-size: clamp(3.1rem, 15vw, 4.5rem);
		}

		.topic-card {
			display: block;
			min-height: 0;
		}

		.topic-card__image {
			height: 260px;
		}

		.topic-card__content {
			min-height: 290px;
			padding: 18px 24px 26px;
		}
	}
</style>
