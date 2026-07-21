<script lang="ts">
	const photos = [
		{
			src: "/images/gallery/moment-01.webp",
			alt: "DigiPack participants spending time together in nature"
		},
		{
			src: "/images/gallery/moment-02.webp",
			alt: "The natural landscape around Stara Zagora"
		},
		{
			src: "/images/gallery/moment-03.webp",
			alt: "Participants exploring the surrounding forest"
		},
		{
			src: "/images/gallery/moment-04.webp",
			alt: "Youth workers collaborating during a workshop"
		},
		{
			src: "/images/gallery/moment-05.webp",
			alt: "Participants taking part in an outdoor group activity"
		},
		{
			src: "/images/gallery/moment-06.webp",
			alt: "Participants sharing a cultural evening"
		}
	];
</script>

<section class="gallery" id="gallery">
	<div class="gallery__inner">
		<div class="section-label">
			<span></span>
			<p>05 / Field moments</p>
		</div>

		<div class="gallery__heading">
			<h2>
				Real moments.
				<em>Shared memories.</em>
			</h2>

			<p>
				Between workshops, nature walks, cultural evenings and shared
				laughter, the project became more than a training course.
			</p>
		</div>

		<div class="gallery__grid">
			{#each photos as photo, index}
				<figure class:featured={index === 0} class={`photo photo-${index + 1}`}>
					<img
						src={photo.src}
						alt={photo.alt}
						loading={index === 0 ? "eager" : "lazy"}
					/>

					<figcaption>
						{String(index + 1).padStart(2, "0")}
					</figcaption>
				</figure>
			{/each}
		</div>
	</div>
</section>

<style>
	.gallery {
		--cream: #f3f0e7;
		--forest: #123f37;
		--gold: #dca545;
		--grey: #5b6561;

		padding: clamp(100px, 12vw, 170px) 32px;
		background: var(--cream);
	}

	.gallery__inner {
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
		font-family: monospace;
		font-size: 0.72rem;
		letter-spacing: 0.18em;
		text-transform: uppercase;
	}

	.gallery__heading {
		display: grid;
		grid-template-columns: 1.2fr 0.8fr;
		gap: clamp(50px, 9vw, 150px);
		align-items: start;
	}

	h2 {
		margin: 0;
		color: var(--forest);
		font-family: Georgia, serif;
		font-size: clamp(3.7rem, 5.7vw, 6.2rem);
		font-weight: 400;
		letter-spacing: -0.055em;
		line-height: 0.88;
	}

	h2 em {
		display: block;
		margin-top: 12px;
		color: var(--gold);
		font-weight: 400;
	}

	.gallery__heading > p {
		max-width: 520px;
		margin: 12px 0 0;
		color: var(--grey);
		font-size: 1.05rem;
		line-height: 1.65;
	}

	.gallery__grid {
		display: grid;
		grid-template-columns: repeat(4, minmax(0, 1fr));
		grid-template-rows: 280px 280px 280px;
		gap: 18px;
		margin-top: clamp(70px, 8vw, 110px);
	}

	.photo {
		position: relative;
		margin: 0;
		overflow: hidden;
		border-radius: 6px;
		background: #d8ddd7;
	}

	.photo-1 {
		grid-column: 1 / 3;
		grid-row: 1 / 3;
	}

	.photo-2 {
		grid-column: 3;
		grid-row: 1;
	}

	.photo-3 {
		grid-column: 4;
		grid-row: 1;
	}

	.photo-4 {
		grid-column: 3 / 5;
		grid-row: 2;
	}

	.photo-5 {
		grid-column: 1 / 3;
		grid-row: 3;
	}

	.photo-6 {
		grid-column: 3 / 5;
		grid-row: 3;
	}

	img {
		width: 100%;
		height: 100%;
		object-fit: cover;
		transition: transform 600ms ease;
	}

	.photo:hover img {
		transform: scale(1.04);
	}

	figcaption {
		position: absolute;
		top: 14px;
		left: 14px;
		padding: 7px 9px;
		border-radius: 4px;
		background: rgba(243, 240, 231, 0.9);
		color: var(--forest);
		font-family: monospace;
		font-size: 0.65rem;
		letter-spacing: 0.12em;
	}

	@media (max-width: 900px) {
		.gallery__heading {
			grid-template-columns: 1fr;
			gap: 32px;
		}

		.gallery__grid {
			grid-template-columns: repeat(2, minmax(0, 1fr));
			grid-template-rows: 430px 250px 250px 250px;
		}

		.photo-1 {
			grid-column: 1 / 3;
			grid-row: 1;
		}

		.photo-2 {
			grid-column: 1;
			grid-row: 2;
		}

		.photo-3 {
			grid-column: 2;
			grid-row: 2;
		}

		.photo-4 {
			grid-column: 1 / 3;
			grid-row: 3;
		}

		.photo-5 {
			grid-column: 1;
			grid-row: 4;
		}

		.photo-6 {
			grid-column: 2;
			grid-row: 4;
		}
	}

	@media (max-width: 560px) {
		.gallery {
			padding-inline: 20px;
		}

		h2 {
			font-size: clamp(3.4rem, 16vw, 4.7rem);
		}

		.gallery__grid {
			display: flex;
			flex-direction: column;
		}

		.photo {
			height: 270px;
		}

		.photo:first-child {
			height: 420px;
		}
	}
</style>
