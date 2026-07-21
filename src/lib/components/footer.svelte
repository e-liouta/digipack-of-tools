<footer class="footer">
	<div class="footer__inner">
		<div class="footer__main">
			<div class="footer__project">
				<h2>
					DigiPack of Tools
					<em>for Youth Workers</em>
				</h2>

				<p class="host">
					Hosted by Academy of Success · Youthopia Riverside · Bulgaria
				</p>

				<a class="email" href="mailto:info@asbg.eu">
					info@asbg.eu
				</a>
			</div>

			<div class="footer__partners">
				<p class="partner-label">Official logos</p>

				<div class="logos">
					<div class="logo-item">
						<img
							src="/logos/eu-logo.png"
							alt="Co-funded by the European Union"
						/>
					</div>

					<div class="logo-item">
						<img
							src="/logos/logo-na.png"
							alt="Erasmus+ National Agency"
						/>
					</div>

					<div class="logo-item">
						<img
							src="/logos/logo-organisation.jpg"
							alt="Academy of Success"
						/>
					</div>
				</div>
			</div>
		</div>

		<div class="footer__bottom">
			<p>
				© 2026 DigiPack · Erasmus+ KA1 Mobility of Youth Workers
			</p>

		</div>
		<div class="footer__disclaimer">
			<p>
				Funded by the European Union. Views and opinions expressed are
				however those of the author(s) only and do not necessarily reflect
				those of the European Union or the European Education and Culture
				Executive Agency (EACEA). Neither the European Union nor EACEA can be
				held responsible for them.
			</p>
</div>
	</div>
</footer>

<style>
	.footer {
		--forest: #123f37;
		--cream: #f3f0e7;
		--aqua: #48c8cb;
		--sage: #91a78e;

		padding: 80px 32px 42px;
		background-color: var(--forest);
		background-image:
			linear-gradient(rgba(72, 200, 203, 0.025) 1px, transparent 1px),
			linear-gradient(90deg, rgba(72, 200, 203, 0.025) 1px, transparent 1px);
		background-size: 56px 56px;
	}

	.footer__inner {
		width: min(1420px, 100%);
		margin-inline: auto;
	}

	.footer__main {
		display: grid;
		grid-template-columns: 0.9fr 1.1fr;
		gap: clamp(70px, 10vw, 170px);
	}

	h2 {
		margin: 0;
		color: var(--cream);
		font-family: Georgia, serif;
		font-size: clamp(2.5rem, 3.4vw, 4rem);
		font-weight: 400;
		letter-spacing: -0.04em;
		line-height: 0.98;
	}

	h2 em {
		display: block;
		margin-top: 8px;
		color: var(--aqua);
		font-weight: 400;
	}

	.host {
		margin: 40px 0 0;
		color: var(--sage);
		font-family: monospace;
		font-size: 0.68rem;
		letter-spacing: 0.17em;
		line-height: 1.7;
		text-transform: uppercase;
	}

	.email {
		display: inline-block;
		margin-top: 30px;
		padding-bottom: 7px;
		border-bottom: 1px solid rgba(72, 200, 203, 0.55);
		color: var(--cream);
		font-size: 1.05rem;
		text-decoration: none;
		transition:
			color 200ms ease,
			border-color 200ms ease;
	}

	.email:hover {
		border-color: var(--aqua);
		color: var(--aqua);
	}

	.partner-label {
		margin: 0;
		color: var(--sage);
		font-family: monospace;
		font-size: 0.65rem;
		letter-spacing: 0.17em;
		text-transform: uppercase;
	}

	.logos {
		display: grid;
		grid-template-columns: repeat(3, 1fr);
		gap: 14px;
		margin-top: 20px;
	}

	.logo-item {
		display: flex;
		align-items: center;
		justify-content: center;
		min-height: 145px;
		padding: 22px;
		border: 1px solid rgba(145, 167, 142, 0.24);
		border-radius: 4px;
		background: #ffffff;
}

.logo-item img {
		display: block;
		width: 100%;
		height: 82px;
		object-fit: contain;
}
	.footer__bottom {
		display: flex;
		align-items: center;
		justify-content: space-between;
		gap: 30px;
		margin-top: 75px;
		padding-top: 28px;
		border-top: 1px solid rgba(243, 240, 231, 0.12);
	}

	.footer__bottom p {
		margin: 0;
		color: rgba(145, 167, 142, 0.8);
		font-family: monospace;
		font-size: 0.62rem;
		letter-spacing: 0.16em;
		line-height: 1.6;
		text-transform: uppercase;
	}

	.footer__disclaimer {
		margin-top: 32px;
		padding-top: 24px;
		border-top: 1px solid rgba(243, 240, 231, 0.08);
}

.footer__disclaimer p {
		max-width: 900px;
		margin: 0 auto;
		color: rgba(243, 240, 231, 0.58);
		font-size: 0.78rem;
		line-height: 1.7;
		text-align: center;
}

	@media (max-width: 850px) {
		.footer__main {
			grid-template-columns: 1fr;
		}

		.footer__project {
			max-width: 600px;
		}
	}

	@media (max-width: 600px) {
		.footer {
			padding: 70px 20px 35px;
		}

		.logos {
			grid-template-columns: 1fr;
		}


		.footer__bottom {
			align-items: flex-start;
			flex-direction: column;
			margin-top: 60px;
		}
	}
</style>
