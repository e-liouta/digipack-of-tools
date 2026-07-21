<script lang="ts">
	const statistics = [
		{
			number: "31",
			label: "Participants"
		},
		{
			number: "8",
			label: "Countries"
		},
		{
			number: "9",
			label: "Days together"
		},
		{
			number: "1",
			label: "Shared journey"
		}
	];
</script>

<section class="about" id="about">
	<div class="about__inner">
		<div class="section-label">
			<span></span>
			<p>01 / About the project</p>
		</div>

		<div class="about__introduction">
			<h2>
				Where digital exploration meets
				<em>human connection.</em>
			</h2>

			<div class="about__text">
				<p>
					DigiPack brought together 31 youth workers from eight countries
					to explore how technology can support safer, more creative and
					more meaningful youth work.
				</p>

				<p>
					Through non-formal learning, practical workshops and shared
					experiences, participants transformed digital challenges into
					useful tools, new ideas and stronger connections.
				</p>
			</div>
		</div>

		<div class="statistics">
			<div class="statistics__line" aria-hidden="true"></div>

			{#each statistics as statistic, index}
				<article class="statistic">
					<span class="statistic__index">
						{String(index + 1).padStart(2, "0")}
					</span>

					<strong>{statistic.number}</strong>
					<p>{statistic.label}</p>
				</article>
			{/each}
		</div>
	</div>
</section>

<style>
	.about {
		--cream: #f3f0e7;
		--card: #f8f6f0;
		--forest: #123f37;
		--sage: #668675;
		--aqua: #48c8cb;
		--grey: #59635f;

		position: relative;
		padding: clamp(100px, 13vw, 180px) 32px;
		overflow: hidden;
		background-color: var(--cream);
		background-image:
			linear-gradient(rgba(18, 63, 55, 0.025) 1px, transparent 1px),
			linear-gradient(90deg, rgba(18, 63, 55, 0.025) 1px, transparent 1px);
		background-size: 56px 56px;
	}

	.about__inner {
		width: min(1420px, 100%);
		margin-inline: auto;
	}

	.section-label {
		display: flex;
		align-items: center;
		gap: 14px;
		margin-bottom: 34px;
	}

	.section-label span {
		width: 34px;
		height: 1px;
		background: rgba(18, 63, 55, 0.35);
	}

	.section-label p {
		margin: 0;
		color: #587068;
		font-family: monospace;
		font-size: 0.72rem;
		letter-spacing: 0.18em;
		text-transform: uppercase;
	}

	.about__introduction {
		display: grid;
		grid-template-columns: minmax(0, 1.4fr) minmax(300px, 0.8fr);
		gap: clamp(60px, 9vw, 150px);
		align-items: start;
	}

	h2 {
		max-width: 820px;
		margin: 0;
		color: var(--forest);
		font-family: Georgia, serif;
		font-size: clamp(3.4rem, 5vw, 5.8rem);
		font-weight: 400;
		letter-spacing: -0.05em;
		line-height: 0.95;
	}

	h2 em {
		color: var(--sage);
		font-weight: 400;
	}

	.about__text {
		padding-top: 18px;
	}

	.about__text p {
		margin: 0;
		color: var(--grey);
		font-size: 1.05rem;
		line-height: 1.65;
	}

	.about__text p + p {
		margin-top: 24px;
	}

	.statistics {
		position: relative;
		display: grid;
		grid-template-columns: repeat(4, 1fr);
		gap: 28px;
		margin-top: clamp(80px, 10vw, 130px);
	}

	.statistics__line {
		position: absolute;
		z-index: 0;
		top: 50%;
		left: 5%;
		width: 90%;
		border-top: 2px dotted var(--aqua);
		opacity: 0.8;
	}

	.statistic {
		position: relative;
		z-index: 1;
		min-height: 190px;
		padding: 18px;
		border: 1px solid rgba(18, 63, 55, 0.14);
		border-radius: 7px;
		background: var(--card);
		text-align: center;
	}

	.statistic__index {
		position: absolute;
		top: 16px;
		left: 16px;
		color: #9caea7;
		font-family: monospace;
		font-size: 0.65rem;
		letter-spacing: 0.15em;
	}

	.statistic strong {
		display: block;
		margin-top: 16px;
		color: var(--forest);
		font-family: Georgia, serif;
		font-size: clamp(3.5rem, 5vw, 5rem);
		font-weight: 400;
		line-height: 1;
	}

	.statistic p {
		margin: 18px 0 0;
		color: #71867e;
		font-family: monospace;
		font-size: 0.68rem;
		letter-spacing: 0.2em;
		text-transform: uppercase;
	}

	@media (max-width: 900px) {
		.about__introduction {
			grid-template-columns: 1fr;
			gap: 38px;
		}

		.about__text {
			max-width: 650px;
			padding-top: 0;
		}

		.statistics {
			grid-template-columns: repeat(2, 1fr);
		}

		.statistics__line {
			display: none;
		}
	}

	@media (max-width: 560px) {
		.about {
			padding-inline: 20px;
		}

		h2 {
			font-size: clamp(3rem, 14vw, 4.2rem);
		}

		.statistics {
			grid-template-columns: 1fr;
			gap: 16px;
			margin-top: 65px;
		}

		.statistic {
			min-height: 160px;
		}
	}
</style>
