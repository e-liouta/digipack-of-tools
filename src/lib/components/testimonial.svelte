<script lang="ts">
	let isPlaying = $state(false);
	let videoElement = $state<HTMLVideoElement>();

	function toggleVideo() {
		if (!videoElement) return;

		if (videoElement.paused) {
			videoElement.play();
		} else {
			videoElement.pause();
		}
	}

	function handlePlay() {
		isPlaying = true;
	}

	function handlePause() {
		isPlaying = false;
	}
</script>

<section class="testimonial" id="testimonial">
	<div class="testimonial__inner">
		<div class="section-label">
			<span></span>
			<p>07 / Voices from the journey</p>
		</div>

		<div class="testimonial__heading">
			<h2>
				More than a
				<em>training course.</em>
			</h2>

			<p>
				A shared experience shaped by new friendships, practical tools,
				open conversations and ideas that travel beyond Stara Zagora.
			</p>
		</div>

		<div class="testimonial__content">
			<div class="testimonial__video">
				<video
					bind:this={videoElement}
					src="/videos/digipack-testimonial.MP4"
					preload="metadata"
					playsinline
					controls
					onplay={handlePlay}
					onpause={handlePause}
					onended={handlePause}
				>
					<track
						kind="captions"
						srclang="en"
						label="English"
					/>

					Your browser does not support the video element.
				</video>

				<button
					class:playing={isPlaying}
					class="video-button"
					type="button"
					aria-label={isPlaying ? "Pause testimonial video" : "Play testimonial video"}
					onclick={toggleVideo}
				>
					{#if isPlaying}
						<svg
							viewBox="0 0 24 24"
							aria-hidden="true"
						>
							<rect x="7" y="5" width="3.5" height="14" rx="1"></rect>
							<rect x="13.5" y="5" width="3.5" height="14" rx="1"></rect>
						</svg>
					{:else}
						<svg
							viewBox="0 0 24 24"
							aria-hidden="true"
						>
							<path d="M8 5.5L18 12L8 18.5V5.5Z"></path>
						</svg>
					{/if}
				</button>

				<div class="video-tag">
					<span></span>
					Participant story
				</div>
			</div>
		</div>
	</div>
</section>

<style>
	.testimonial {
		--cream: #f3f0e7;
		--forest: #123f37;
		--deep-forest: #0b302a;
		--aqua: #48c8cb;
		--blue: #82bcc5;
		--grey: #5b6561;

		position: relative;
		padding: clamp(100px, 12vw, 170px) 32px;
		overflow: hidden;
		background: var(--forest);
	}

	.testimonial::before {
		position: absolute;
		top: -240px;
		right: -180px;
		width: 520px;
		height: 520px;
		border: 1px solid rgba(72, 200, 203, 0.13);
		border-radius: 50%;
		content: "";
	}

	.testimonial::after {
		position: absolute;
		bottom: -280px;
		left: -190px;
		width: 520px;
		height: 520px;
		border: 1px solid rgba(243, 240, 231, 0.08);
		border-radius: 50%;
		content: "";
	}

	.testimonial__inner {
		position: relative;
		z-index: 1;
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
		background: rgba(72, 200, 203, 0.65);
	}

	.section-label p {
		margin: 0;
		color: var(--aqua);
		font-family: var(--font-mono);
		font-size: 0.72rem;
		letter-spacing: 0.18em;
		text-transform: uppercase;
	}

	.testimonial__heading {
		display: grid;
		grid-template-columns: minmax(0, 1.4fr) minmax(260px, 0.6fr);
		align-items: end;
		gap: clamp(40px, 7vw, 120px);
	}

	h2 {
		max-width: 850px;
		margin: 0;
		color: var(--cream);
		font-family: var(--font-display);
		font-size: clamp(3.5rem, 5.5vw, 6rem);
		font-weight: 400;
		letter-spacing: -0.05em;
		line-height: 0.95;
	}

	h2 em {
		display: block;
		color: var(--blue);
		font-weight: 400;
	}

	.testimonial__heading > p {
		max-width: 460px;
		margin: 0 0 5px;
		color: rgba(243, 240, 231, 0.65);
		font-size: 1rem;
		line-height: 1.7;
	}

	.testimonial__content {
		display: flex;
		justify-content: center;
		margin-top: clamp(70px, 8vw, 110px);
	}

	.testimonial__video {
		position: relative;
		min-height: 560px;
		overflow: hidden;
		border: 1px solid rgba(72, 200, 203, 0.2);
		border-radius: 8px;
		background: var(--deep-forest);
		box-shadow: 0 35px 90px rgba(0, 0, 0, 0.2);
	}

	.testimonial__video video {
		display: block;
		width: 100%;
		height: 100%;
		min-height: 560px;
		background: var(--deep-forest);
		object-fit: cover;
	}

	.video-button {
		position: absolute;
		top: 50%;
		left: 50%;
		display: grid;
		width: 86px;
		height: 86px;
		padding: 0;
		transform: translate(-50%, -50%);
		border: 1px solid rgba(255, 255, 255, 0.35);
		border-radius: 50%;
		background: rgba(243, 240, 231, 0.9);
		box-shadow: 0 18px 50px rgba(0, 0, 0, 0.2);
		color: var(--forest);
		cursor: pointer;
		place-items: center;
		transition:
			transform 220ms ease,
			opacity 220ms ease,
			background 220ms ease;
		backdrop-filter: blur(12px);
	}

	.video-button:hover {
		transform: translate(-50%, -50%) scale(1.08);
		background: var(--cream);
	}

	.video-button.playing {
		opacity: 0;
		pointer-events: none;
	}

	.testimonial__video:hover .video-button.playing,
	.testimonial__video:focus-within .video-button.playing {
		opacity: 1;
		pointer-events: auto;
	}

	.video-button svg {
		width: 30px;
		height: 30px;
		fill: currentColor;
	}

	.video-tag {
		position: absolute;
		top: 24px;
		left: 24px;
		display: flex;
		align-items: center;
		gap: 9px;
		padding: 8px 12px;
		border: 1px solid rgba(255, 255, 255, 0.18);
		border-radius: 999px;
		background: rgba(8, 38, 33, 0.62);
		color: var(--cream);
		font-family: var(--font-mono);
		font-size: 0.6rem;
		letter-spacing: 0.12em;
		text-transform: uppercase;
		backdrop-filter: blur(10px);
	}

	.video-tag span {
		width: 7px;
		height: 7px;
		border-radius: 50%;
		background: var(--aqua);
		box-shadow: 0 0 12px rgba(72, 200, 203, 0.8);
	}

	@media (max-width: 1050px) {
		.testimonial__heading,
		.testimonial__content {
			grid-template-columns: 1fr;
		}

		.testimonial__heading > p {
			max-width: 600px;
		}

		.testimonial__video,
		.testimonial__video video {
			min-height: 500px;
		}


	}

	@media (max-width: 650px) {
		.testimonial {
			padding-inline: 20px;
		}

		h2 {
			font-size: clamp(3.1rem, 14vw, 4.5rem);
		}

		.testimonial__video,
		.testimonial__video video {
			min-height: 420px;
		}

		.video-button {
			width: 70px;
			height: 70px;
		}

		.video-button svg {
			width: 25px;
			height: 25px;
		}

		.video-tag {
			top: 16px;
			left: 16px;
		}
	}

	@media (prefers-reduced-motion: reduce) {
		.video-button {
			transition: none;
		}
	}
</style>
