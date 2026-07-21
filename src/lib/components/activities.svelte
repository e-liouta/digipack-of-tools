<script lang="ts">
	const activities = [
		{
			title: "Interactive Workshops",
			description:
				"Turning complex digital topics into practical group activities."
		},
		{
			title: "Creative Challenges",
			description:
				"Solving problems together through design, storytelling and play."
		},
		{
			title: "Peer Learning",
			description:
				"Exchanging knowledge across different cultures and experiences."
		},
		{
			title: "Reflection & Discussion",
			description:
				"Questioning technology, sharing perspectives and learning from one another."
		},
		{
			title: "Nature & Connection",
			description:
				"Stepping away from screens to reconnect with people and place."
		}
	];
</script>

<section class="activities" id="activities">
	<div class="activities__inner">
		<p class="coordinates">
			N 42°25′30″ · E 25°37′12″ · Field notebook
		</p>

		<div class="section-label">
			<span></span>
			<p>03 / Learning by doing</p>
		</div>

		<div class="activities__heading">
			<h2>
				Not lectures.
				<em>Experiences.</em>
			</h2>

			<p>
				The programme was based on non-formal education: active
				participation, experimentation, reflection and exchange.
			</p>
		</div>

		<div class="activity-list">
			<div class="activity-list__line" aria-hidden="true"></div>

			{#each activities as activity, index}
				<article class="activity-card">
					<span class="activity-card__number">
						{String(index + 1).padStart(2, "0")}
					</span>

					<div>
						<h3>{activity.title}</h3>
						<p>{activity.description}</p>
					</div>

					<span class="activity-card__entry">
						Entry · {String(index + 1).padStart(2, "0")}
					</span>
				</article>
			{/each}
		</div>
	</div>
</section>

<style>
	.activities {
		--cream: #f3f0e7;
		--card: #faf8f3;
		--forest: #123f37;
		--coral: #d67b64;
		--aqua: #48c8cb;
		--grey: #5b6561;

		padding: clamp(100px, 12vw, 170px) 32px;
		background-color: var(--cream);
		background-image:
			linear-gradient(rgba(18, 63, 55, 0.04) 1px, transparent 1px),
			linear-gradient(90deg, rgba(18, 63, 55, 0.04) 1px, transparent 1px);
		background-size: 56px 56px;
	}

	.activities__inner {
		width: min(1420px, 100%);
		margin-inline: auto;
	}

	.coordinates {
		margin: 0 0 24px;
		color: #8da099;
		font-family: monospace;
		font-size: 0.65rem;
		letter-spacing: 0.18em;
		text-transform: uppercase;
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
		font-family: monospace;
		font-size: 0.72rem;
		letter-spacing: 0.18em;
		text-transform: uppercase;
	}

	.activities__heading {
		display: grid;
		grid-template-columns: 1.2fr 0.8fr;
		gap: clamp(50px, 9vw, 150px);
		align-items: end;
	}

	h2 {
		max-width: 760px;
		margin: 0;
		color: var(--forest);
		font-family: Georgia, serif;
		font-size: clamp(4rem, 6vw, 6.8rem);
		font-weight: 400;
		letter-spacing: -0.055em;
		line-height: 0.86;
	}

	h2 em {
		display: block;
		margin-top: 10px;
		color: var(--coral);
		font-weight: 400;
	}

	.activities__heading > p {
		max-width: 520px;
		margin: 0 0 10px;
		color: var(--grey);
		font-size: 1.05rem;
		line-height: 1.65;
	}

	.activity-list {
		position: relative;
		display: flex;
		flex-direction: column;
		gap: 24px;
		margin-top: clamp(75px, 9vw, 120px);
		padding-left: 110px;
	}

	.activity-list__line {
		position: absolute;
		top: 0;
		bottom: 0;
		left: 68px;
		border-left: 2px dotted var(--aqua);
	}

	.activity-list__line::before,
	.activity-list__line::after {
		position: absolute;
		left: 50%;
		width: 8px;
		height: 8px;
		border-radius: 50%;
		background: var(--aqua);
		content: "";
		transform: translateX(-50%);
	}

	.activity-list__line::before {
		top: 0;
	}

	.activity-list__line::after {
		bottom: 0;
	}

	.activity-card {
		position: relative;
		display: grid;
		grid-template-columns: 56px 1fr auto;
		gap: 12px;
		align-items: start;
		min-height: 145px;
		padding: 34px 30px;
		border: 1px solid rgba(18, 63, 55, 0.13);
		border-radius: 7px;
		background: rgba(250, 248, 243, 0.94);
		transition:
			transform 200ms ease,
			border-color 200ms ease;
	}

	.activity-card:hover {
		transform: translateX(8px);
		border-color: rgba(72, 200, 203, 0.7);
	}

	.activity-card__number {
		padding-top: 6px;
		color: var(--aqua);
		font-family: monospace;
		font-size: 1rem;
	}

	h3 {
		margin: 0;
		color: var(--forest);
		font-family: Georgia, serif;
		font-size: clamp(1.7rem, 2.4vw, 2.25rem);
		font-weight: 400;
	}

	.activity-card div p {
		margin: 13px 0 0;
		color: var(--grey);
		font-size: 0.98rem;
		line-height: 1.5;
	}

	.activity-card__entry {
		color: #9baca6;
		font-family: monospace;
		font-size: 0.62rem;
		letter-spacing: 0.16em;
		text-transform: uppercase;
	}

	@media (max-width: 850px) {
		.activities__heading {
			grid-template-columns: 1fr;
			gap: 35px;
		}

		.activity-list {
			padding-left: 45px;
		}

		.activity-list__line {
			left: 16px;
		}

		.activity-card {
			grid-template-columns: 48px 1fr;
		}

		.activity-card__entry {
			display: none;
		}
	}

	@media (max-width: 560px) {
		.activities {
			padding-inline: 20px;
		}

		h2 {
			font-size: clamp(3.5rem, 17vw, 5rem);
		}

		.activity-list {
			padding-left: 26px;
		}

		.activity-list__line {
			left: 4px;
		}

		.activity-card {
			grid-template-columns: 1fr;
			min-height: 0;
			padding: 27px 22px;
		}

		.activity-card__number {
			padding-top: 0;
		}
	}
</style>
