<script lang="ts">
	import { fade, scale } from "svelte/transition";

	const photos = [
		{
			src: "/images/gallery/1.jpg",
			alt: "DigiPack participants starting the day with an energizer"
		},
		{
			src: "/images/gallery/2.jpg",
			alt: "Paintings about ourselves"
		},
		{
			src: "/images/gallery/3.jpg",
			alt: "Participants spending time together by the firepit"
		},
		{
			src: "/images/gallery/9.jpg",
			alt: "Group photo of particitants and their flags"
		},
		{
			src: "/images/gallery/4.jpg",
			alt: "Participants taking part in an activity"
		},
		{
			src: "/images/gallery/5.jpg",
			alt: "Participants taking part in a collaborative activity"
		},
		{
			src: "/images/gallery/6.jpg",
			alt: "Participants taking part in an activity"
		},
		{
			src: "/images/gallery/7.jpg",
			alt: "Participants having fun and dancing traditional dances."
		},

	];

	let activePhoto = $state<number | null>(null);

	function openPhoto(index: number) {
		activePhoto = index;
	}

	function closePhoto() {
		activePhoto = null;
	}

	function showNextPhoto() {
		if (activePhoto === null) return;

		activePhoto = (activePhoto + 1) % photos.length;
	}

	function showPreviousPhoto() {
		if (activePhoto === null) return;

		activePhoto = (activePhoto - 1 + photos.length) % photos.length;
	}

	function handleKeydown(event: KeyboardEvent) {
		if (activePhoto === null) return;

		if (event.key === "Escape") {
			closePhoto();
		}

		if (event.key === "ArrowRight") {
			showNextPhoto();
		}

		if (event.key === "ArrowLeft") {
			showPreviousPhoto();
		}
	}
</script>

<svelte:window onkeydown={handleKeydown} />

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
				<button
					class={`photo photo-${index + 1}`}
					type="button"
					aria-label={`Open image ${index + 1} of ${photos.length}`}
					onclick={() => openPhoto(index)}
				>
					<img
						src={photo.src}
						alt={photo.alt}
						loading={index === 0 ? "eager" : "lazy"}
					/>
				</button>
			{/each}
		</div>
	</div>
</section>

{#if activePhoto !== null}
	<div
		class="lightbox"
		role="dialog"
		aria-modal="true"
		aria-label="Image gallery"
		onclick={closePhoto}
		onkeydown={handleKeydown}
		transition:fade={{ duration: 220 }}
	>
		<button
			class="lightbox__close"
			type="button"
			aria-label="Close image"
			onclick={(event) => {
				event.stopPropagation();
				closePhoto();
			}}
		>
			<svg viewBox="0 0 24 24" aria-hidden="true">
				<path d="M6 6L18 18M18 6L6 18" />
			</svg>
		</button>

		<button
			class="lightbox__nav lightbox__nav--previous"
			type="button"
			aria-label="Previous image"
			onclick={(event) => {
				event.stopPropagation();
				showPreviousPhoto();
			}}
		>
			<svg viewBox="0 0 24 24" aria-hidden="true">
				<path d="M15 5L8 12L15 19" />
			</svg>
		</button>

		<div
			class="lightbox__image-wrapper"
			onclick={(event) => event.stopPropagation()}
			onkeydown={handleKeydown}
			role="presentation"
			transition:scale={{ duration: 220, start: 0.96 }}
		>
			<img
				src={photos[activePhoto].src}
				alt={photos[activePhoto].alt}
			/>

			<p class="lightbox__counter">
				{activePhoto + 1} / {photos.length}
			</p>
		</div>

		<button
			class="lightbox__nav lightbox__nav--next"
			type="button"
			aria-label="Next image"
			onclick={(event) => {
				event.stopPropagation();
				showNextPhoto();
			}}
		>
			<svg viewBox="0 0 24 24" aria-hidden="true">
				<path d="M9 5L16 12L9 19" />
			</svg>
		</button>
	</div>
{/if}

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
			grid-auto-rows: 320px;
			gap: 18px;
		margin-top: clamp(70px, 8vw, 110px);
	}

	.photo {
		position: relative;
		display: block;
		width: 100%;
		height: 100%;
		margin: 0;
		padding: 0;
		overflow: hidden;
		border: 0;
		border-radius: 6px;
		background: #d8ddd7;
		cursor: zoom-in;
	}

	.photo-1 {
		grid-column: 1 / 3;
		grid-row: span 2;
	}

	.photo-2 {
		grid-column: 3;
		grid-row: span 1;
	}

	.photo-3 {
		grid-column: 4;
		grid-row: span 1;
	}

	.photo-4 {
		grid-column: 3 / 5;
		grid-row: span 2;
	}

	.photo-5 {
		grid-column: 1;
		grid-row: span 1;
	}

	.photo-6 {
		grid-column: 2;
		grid-row: span 1;
	}

	.photo-7 {
		grid-column: 1 / 3;
		grid-row: span 1;
	}

	.photo-8 {
		grid-column: 3/5;
		grid-row: span 1;
	}



	.photo img {
		display: block;
		width: 100%;
		height: 100%;
		object-fit: cover;
		transition:
			transform 600ms ease,
			filter 400ms ease;
	}

	.photo:hover img {
		transform: scale(1.04);
		filter: brightness(0.92);
	}

	.photo:focus-visible {
		outline: 3px solid var(--gold);
		outline-offset: 4px;
	}

	.lightbox {
		position: fixed;
		inset: 0;
		z-index: 9999;
		display: flex;
		align-items: center;
		justify-content: center;
		padding: 40px 100px;
		background: rgba(5, 18, 16, 0.94);
		backdrop-filter: blur(12px);
	}

	.lightbox__image-wrapper {
		position: relative;
		display: flex;
		align-items: center;
		justify-content: center;
		max-width: 100%;
		max-height: 100%;
	}

	.lightbox__image-wrapper img {
		display: block;
		max-width: min(1200px, 82vw);
		max-height: 86vh;
		border-radius: 6px;
		object-fit: contain;
		box-shadow: 0 30px 80px rgba(0, 0, 0, 0.4);
	}

	.lightbox__counter {
		position: absolute;
		right: 0;
		bottom: -34px;
		margin: 0;
		color: rgba(243, 240, 231, 0.72);
		font-family: monospace;
		font-size: 0.7rem;
		letter-spacing: 0.16em;
	}

	.lightbox__nav,
	.lightbox__close {
		position: absolute;
		z-index: 2;
		display: flex;
		align-items: center;
		justify-content: center;
		width: 52px;
		height: 52px;
		padding: 0;
		border: 1px solid rgba(243, 240, 231, 0.22);
		border-radius: 50%;
		background: rgba(243, 240, 231, 0.08);
		color: var(--cream);
		cursor: pointer;
		backdrop-filter: blur(10px);
		transition:
			background 200ms ease,
			border-color 200ms ease,
			transform 200ms ease;
	}

	.lightbox__nav:hover,
	.lightbox__close:hover {
		border-color: rgba(243, 240, 231, 0.45);
		background: rgba(243, 240, 231, 0.16);
		transform: scale(1.05);
	}

	.lightbox__nav:focus-visible,
	.lightbox__close:focus-visible {
		outline: 2px solid var(--gold);
		outline-offset: 4px;
	}

	.lightbox__nav svg,
	.lightbox__close svg {
		width: 24px;
		height: 24px;
		fill: none;
		stroke: currentColor;
		stroke-width: 1.7;
		stroke-linecap: round;
		stroke-linejoin: round;
	}

	.lightbox__nav--previous {
		left: 30px;
	}

	.lightbox__nav--next {
		right: 30px;
	}

	.lightbox__close {
		top: 28px;
		right: 28px;
	}

	@media (max-width: 900px) {
		.gallery__heading {
			grid-template-columns: 1fr;
			gap: 32px;
		}

		.gallery__grid {
			grid-template-columns: repeat(2, minmax(0, 1fr));
			grid-auto-rows: 250px;
		}

		.photo-1,
		.photo-4,
		.photo-7 {
			grid-column: 1 / 3;
			grid-row: span 1;
		}

		.photo-2,
		.photo-3,
		.photo-5,
		.photo-6,
		.photo-8,
		.photo-9 {
			grid-column: auto;
			grid-row: auto;
		}

		.lightbox {
			padding: 80px 70px;
		}

		.lightbox__image-wrapper img {
			max-width: 82vw;
			max-height: 80vh;
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
			flex: none;
		}

		.photo:first-child {
			height: 420px;
		}

		.lightbox {
			padding: 80px 16px 100px;
		}

		.lightbox__image-wrapper img {
			max-width: 100%;
			max-height: 72vh;
		}

		.lightbox__nav {
			top: auto;
			bottom: 24px;
			width: 48px;
			height: 48px;
		}

		.lightbox__nav--previous {
			left: calc(50% - 58px);
		}

		.lightbox__nav--next {
			right: calc(50% - 58px);
		}

		.lightbox__close {
			top: 18px;
			right: 18px;
			width: 46px;
			height: 46px;
		}

		.lightbox__counter {
			right: 50%;
			bottom: -32px;
			transform: translateX(50%);
		}
	}
</style>
