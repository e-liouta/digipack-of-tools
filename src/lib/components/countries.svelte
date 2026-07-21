<script lang="ts">
	const countries = [
		{
			country: "Bulgaria",
			organisation: "Academy of Success",
			x: 365,
			y: 260
		},
		{
			country: "Denmark",
			organisation: "Youth Spectrum",
			x: 275,
			y: 75
		},
		{
			country: "Greece",
			organisation: "ICSD",
			x: 380,
			y: 405
		},
		{
			country: "North Macedonia",
			organisation: "New Rays",
			x: 330,
			y: 315
		},
		{
			country: "Serbia",
			organisation: "Youth Workers Alliance Vranje",
			x: 315,
			y: 220
		},
		{
			country: "Poland",
			organisation: "Just Do It",
			x: 350,
			y: 135
		},
		{
			country: "Türkiye",
			organisation: "Youth Season",
			x: 470,
			y: 355
		},
		{
			country: "Portugal",
			organisation: "HAWK STARS",
			x: 125,
			y: 285
		}
	];

	const connections = [
		[0, 1],
		[0, 2],
		[0, 3],
		[0, 4],
		[0, 5],
		[0, 6],
		[0, 7],
		[1, 2],
		[1, 3],
		[1, 4],
		[1, 7],
		[2, 3],
		[2, 6],
		[2, 7],
		[3, 4],
		[3, 5],
		[3, 6],
		[3, 7],
		[4, 5],
		[4, 7],
		[5, 6],
		[6, 7]
	];
</script>

<section class="countries">
	<div class="countries__inner">
		<div class="section-label">
			<span></span>
			<p>06 / One European community</p>
		</div>

		<h2>
			Eight countries.
			<em>One flowing story.</em>
		</h2>

		<div class="countries__content">
			<div class="network">
				<svg
					viewBox="0 0 600 480"
					role="img"
					aria-label="A network connecting the eight participating countries"
				>
					{#each connections as connection}
						<line
							x1={countries[connection[0]].x}
							y1={countries[connection[0]].y}
							x2={countries[connection[1]].x}
							y2={countries[connection[1]].y}
						></line>
					{/each}

					{#each countries as item}
						<g class="network__node">
							<circle
								class="network__pulse"
								cx={item.x}
								cy={item.y}
								r="16"
							></circle>

							<circle
								class="network__point"
								cx={item.x}
								cy={item.y}
								r="7"
							></circle>

							<text x={item.x + 14} y={item.y + 5}>
								{item.country}
							</text>
						</g>
					{/each}
				</svg>

				<p>Network · 08 nodes · Active</p>
			</div>

			<div class="partners">
				<p class="partners__introduction">
					Different backgrounds. Shared knowledge. Stronger youth work.
				</p>

				<ul>
					{#each countries as item}
						<li>
							<div>
								<span>{item.country}</span>

								{#if item.organisation}
									<strong>{item.organisation}</strong>
								{:else}
									<strong class="missing">
										Organisation name to add
									</strong>
								{/if}
							</div>

							<span class="status" aria-label="Connected"></span>
						</li>
					{/each}
				</ul>
			</div>
		</div>
	</div>
</section>

<style>
	.countries {
		--forest: #0c332d;
		--cream: #f3f0e7;
		--sage: #9aab91;
		--aqua: #48c8cb;

		position: relative;
		padding: clamp(100px, 12vw, 170px) 32px;
		overflow: hidden;
		background-color: var(--forest);
		background-image:
			linear-gradient(rgba(72, 200, 203, 0.03) 1px, transparent 1px),
			linear-gradient(90deg, rgba(72, 200, 203, 0.03) 1px, transparent 1px);
		background-size: 56px 56px;
	}

	.countries__inner {
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
		margin: 0;
		color: var(--cream);
		font-family: Georgia, serif;
		font-size: clamp(3.7rem, 5.6vw, 6.2rem);
		font-weight: 400;
		letter-spacing: -0.05em;
		line-height: 0.92;
	}

	h2 em {
		display: block;
		margin-top: 10px;
		color: var(--aqua);
		font-weight: 400;
	}

	.countries__content {
		display: grid;
		grid-template-columns: minmax(400px, 0.95fr) 1.05fr;
		gap: clamp(55px, 8vw, 120px);
		align-items: stretch;
		margin-top: clamp(70px, 8vw, 110px);
}

.network {
	position: relative;
	display: flex;
	min-height: 550px;
	padding: 30px;
	border: 1px solid rgba(72, 200, 203, 0.2);
	border-radius: 7px;
	background: rgba(8, 45, 39, 0.45);
}

.network svg {
	display: block;
	width: 100%;
	height: 100%;
	min-height: 480px;
}

	.network line {
		stroke: rgba(72, 200, 203, 0.28);
		stroke-width: 1.3;
	}

	.network__pulse {
		fill: none;
		stroke: rgba(72, 200, 203, 0.25);
		stroke-width: 2;
	}

	.network__point {
		fill: var(--aqua);
	}

	.network text {
		fill: var(--sage);
		font-family: monospace;
		font-size: 11px;
	}

	.network > p {
		position: absolute;
		right: 22px;
		bottom: 18px;
		margin: 0;
		color: var(--aqua);
		font-family: monospace;
		font-size: 0.62rem;
		letter-spacing: 0.16em;
		text-transform: uppercase;
	}

	.partners__introduction {
		margin: 0 0 40px;
		color: var(--sage);
		font-size: 1.05rem;
		line-height: 1.6;
	}

	.partners ul {
		margin: 0;
		padding: 0;
		border-top: 1px solid rgba(243, 240, 231, 0.12);
		list-style: none;
	}

	.partners li {
		display: flex;
		align-items: center;
		justify-content: space-between;
		gap: 20px;
		min-height: 92px;
		padding: 18px 4px;
		border-bottom: 1px solid rgba(243, 240, 231, 0.12);
	}

	.partners li div {
		display: flex;
		flex-direction: column;
		gap: 7px;
	}

	.partners li div > span {
		color: var(--aqua);
		font-family: monospace;
		font-size: 0.67rem;
		letter-spacing: 0.17em;
		text-transform: uppercase;
	}

	.partners strong {
		color: var(--cream);
		font-family: Georgia, serif;
		font-size: 1.35rem;
		font-weight: 400;
	}

	.partners strong.missing {
		color: rgba(243, 240, 231, 0.4);
		font-family: monospace;
		font-size: 0.7rem;
		letter-spacing: 0.1em;
		text-transform: uppercase;
	}

	.status {
		width: 9px;
		height: 9px;
		border: 4px solid rgba(72, 200, 203, 0.16);
		border-radius: 50%;
		background: var(--aqua);
		box-sizing: content-box;
	}

	@media (max-width: 950px) {
		.countries__content {
			grid-template-columns: 1fr;
		}

		.network {
			min-height: 500px;
		}
	}

	@media (max-width: 560px) {
		.countries {
			padding-inline: 20px;
		}

		h2 {
			font-size: clamp(3.4rem, 16vw, 4.7rem);
		}

		.countries__content {
			gap: 60px;
		}

		.network {
			min-height: 380px;
			padding: 10px;
		}

		.network svg {
			height: 360px;
		}

		.network text {
			font-size: 9px;
		}

		.partners strong {
			font-size: 1.15rem;
		}
	}
</style>
