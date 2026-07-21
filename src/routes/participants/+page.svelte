<script lang="ts">
	type Participant = {
		name: string;
		image?: string;
	};

	type TeamMember = {
		name: string;
		role: string;
		image?: string;
		organisation?: string;
	};

	type CountryGroup = {
		country: string;
		code: string;
		organisation: string;
		participants: Participant[];
	};

	const defaultImage = "/images/participants/default-user.webp";

	/*
		Add facilitators, trainers and organisers here.

		Example:

		{
			name: "Full Name",
			role: "Facilitator",
			image: "/images/participants/team/full-name.webp",
			organisation: "Academy of Success"
		}
	*/
	const projectTeam: TeamMember[] = [];

	const countryGroups: CountryGroup[] = [
		{
			country: "Bulgaria",
			code: "BG",
			organisation: "Academy of Success",
			participants: [
				{
					name: "Elisaveta Koleva",
					image:
						"/images/participants/default.jpg.webp"
				},
				{
					name: "Ivelina Bronke",
					image: "/images/participants/default.jpg.webp"
				},
				{
					name: "Kristian Stefanov",
					image:
						"/images/participants/default.jpg.webp"
				},
				{
					name: "Milen Stefanov",
					image: "/images/participants/default.jpg.webp"
				},
				{
					name: "Monika Kamenova",
					image: "/images/participants/monika.jpg"
				},
				{
					name: "Zhivko Zhelev",
					image: "/images/participants/default.jpg.webp"
				}
			]
		},
		{
			country: "Denmark",
			code: "DK",
			organisation: "Youth Spectrum",
			participants: [
				{
					name: "Dunya Mohamed",
					image: "/images/participants/default.jpg.webp"
				},
				{
					name: "Hanan Isse",
					image: "/images/participants/default.jpg.webp"
				},
				{
					name: "Jesper Rød",
					image: "/images/participants/default.jpg.webp"
				}
			]
		},
		{
			country: "Greece",
			code: "GR",
			organisation: "ICSD",
			participants: [
				{
					name: "Effie Liouta",
					image: "/images/participants/effie.jpg"
				},
				{
					name: "Eleni Patatoukaki",
					image:
						"/images/participants/default.jpg.webp"
				},
				{
					name: "Rafail Georgios Makridis",
					image:
						"/images/participants/default.jpg.webp"
				},
				{
					name: "Sotirios Kletsas",
					image:
						"/images/participants/sotirios.jpg"
				}
			]
		},
		{
			country: "North Macedonia",
			code: "MK",
			organisation: "New Rays",
			participants: [
				{
					name: "Filip Grozdanovski",
					image:
						"/images/participants/default.jpg.webp"
				},
				{
					name: "Martin Mojanovski",
					image:
						"/images/participants/default.jpg.webp"
				},
				{
					name: "Milcho Duli",
					image:
						"/images/participants/default.jpg.webp"
				},
				{
					name: "Rosica Mojsova",
					image:
						"/images/participants/default.jpg.webp"
				}
			]
		},
		{
			country: "Poland",
			code: "PL",
			organisation: "Just Do It",
			participants: [
				{
					name: "Ewa Pich",
					image: "/images/participants/ewa.jpg"
				},
				{
					name: "Mariana Khrystyk",
					image:
						"/images/participants/mariana.jpg"
				},
				{
					name: "Marta Andrzejewska",
					image:
						"/images/participants/default.jpg.webp"
				}
			]
		},
		{
			country: "Portugal",
			code: "PT",
			organisation: "Hawk Stars",
			participants: [
				{
					name: "Ana Rita Lozano",
					image:
						"/images/participants/rita.jpg"
				},
				{
					name: "Beatriz Freitas",
					image:
						"/images/participants/beatriz.jpg"
				},
				{
					name: "Claudia Monteiro",
					image:
						"/images/participants/default.jpg.webp"
				}
			]
		},
		{
			country: "Serbia",
			code: "RS",
			organisation: "Youth Workers Alliance",
			participants: [
				{
					name: "Anja Adamović",
					image: "/images/participants/default.jpg.webp"
				},
				{
					name: "Luka Nikolic",
					image: "/images/participants/default.jpg.webp"
				},
				{
					name: "Marko Savić",
					image: "/images/participants/default.jpg.webp"
				},
				{
					name: "Pavle Pavlović",
					image: "/images/participants/default.jpg.webp"
				}
			]
		},
		{
			country: "Türkiye",
			code: "TR",
			organisation: "Youth Season",
			participants: [
				{
					name: "Asude Çetindağ",
					image:
						"/images/participants/asude.jpg"
				},
				{
					name: "Kerem Uygur",
					image: "/images/participants/kerem.jpg"
				},
				{
					name: "Özge Çoban",
					image: "/images/participants/ozge.jpg"
				},
				{
					name: "Yağız Ömer Soylak",
					image:
						"/images/participants/default.jpg.webp"
				}
			]
		}
	];

	const totalParticipants = countryGroups.reduce(
		(total, group) => total + group.participants.length,
		0
	);

	const totalPeople = totalParticipants + projectTeam.length;

	function useDefaultImage(event: Event) {
		const image = event.currentTarget as HTMLImageElement;

		if (image.dataset.fallbackApplied === "true") return;

		image.dataset.fallbackApplied = "true";
		image.src = defaultImage;
	}
</script>

<svelte:head>
	<title>Meet the Community | DigiPack of Tools</title>

	<meta
		name="description"
		content="Meet the participants, facilitators, trainers and organisers of the DigiPack of Tools Erasmus+ training course in Bulgaria."
	/>
</svelte:head>

<header class="page-header">
	<div class="page-header__inner">
		<a class="back-link" href="/">
			<svg viewBox="0 0 24 24" aria-hidden="true">
				<path d="M15 5L8 12L15 19" />
			</svg>

			<span>Back to DigiPack</span>
		</a>

		<a class="project-name" href="/">
			<span>DigiPack</span>
			<em>of Tools</em>
		</a>
	</div>
</header>

<main>
	<section class="hero">
		<div class="hero__decoration hero__decoration--one"></div>
		<div class="hero__decoration hero__decoration--two"></div>

		<div class="hero__inner">
			<div class="section-label">
				<span></span>
				<p>The people behind the project</p>
			</div>

			<div class="hero__content">
				<div>
					<p class="hero__eyebrow">
						{String(totalPeople).padStart(2, "0")} people ·
						{String(countryGroups.length).padStart(2, "0")} countries
					</p>

					<h1>
						Meet the people
						<em>who followed the river.</em>
					</h1>
				</div>

				<div class="hero__introduction">
					<p>
						DigiPack brought together youth workers and participants
						from eight countries to learn, create and exchange
						experiences in Stara Zagora.
					</p>

					<p>
						Different experiences, cultures and perspectives became
						one shared digital journey.
					</p>
				</div>
			</div>
		</div>
	</section>

	<section class="community">
		<div class="community__inner">
			{#if projectTeam.length > 0}
				<section
					class="team-section"
					aria-labelledby="project-team-title"
				>
					<header class="group-header">
						<div class="group-header__number">00</div>

						<div class="group-header__title">
							<p>Project team</p>

							<h2 id="project-team-title">
								Facilitators, trainers and organisers
							</h2>
						</div>

						<p class="group-header__count">
							{projectTeam.length}
							{projectTeam.length === 1 ? " person" : " people"}
						</p>
					</header>

					<div class="people-grid">
						{#each projectTeam as person}
							<article class="person">
								<div class="person__image">
									<img
										src={person.image ?? defaultImage}
										alt={person.image
											? `Portrait of ${person.name}`
											: `Default profile image for ${person.name}`}
										loading="lazy"
										onerror={useDefaultImage}
									/>
								</div>

								<div class="person__content">
									<h3>{person.name}</h3>
									<p>{person.role}</p>

									{#if person.organisation}
										<span>{person.organisation}</span>
									{/if}
								</div>
							</article>
						{/each}
					</div>
				</section>
			{/if}

			{#each countryGroups as group, groupIndex}
				<section
					class="country"
					aria-labelledby={`country-${group.code.toLowerCase()}`}
				>
					<header class="group-header">
						<div class="group-header__number">
							{String(groupIndex + 1).padStart(2, "0")}
						</div>

						<div class="group-header__title">
							<p>{group.code} · {group.organisation}</p>

							<h2 id={`country-${group.code.toLowerCase()}`}>
								{group.country}
							</h2>
						</div>

						<p class="group-header__count">
							{group.participants.length}
							{group.participants.length === 1
								? " participant"
								: " participants"}
						</p>
					</header>

					<div class="people-grid">
						{#each group.participants as person}
							<article class="person">
								<div class="person__image">
									<img
										src={person.image ?? defaultImage}
										alt={person.image
											? `Portrait of ${person.name}`
											: `Default profile image for ${person.name}`}
										loading="lazy"
										onerror={useDefaultImage}
									/>
								</div>

								<div class="person__content">
									<h3>{person.name}</h3>
									<span>{group.organisation}</span>
								</div>
							</article>
						{/each}
					</div>
				</section>
			{/each}
		</div>
	</section>

	<section class="closing">
		<div class="closing__inner">
			<p class="closing__small">One course. Many perspectives.</p>

			<h2>
				Different paths.
				<em>One digital river.</em>
			</h2>

			<a href="/#gallery">
				<span>Explore our shared moments</span>

				<svg viewBox="0 0 24 24" aria-hidden="true">
					<path d="M5 12H19M13 6L19 12L13 18" />
				</svg>
			</a>
		</div>
	</section>
</main>

<footer class="footer">
	<div class="footer__inner">
		<p>© 2026 DigiPack · Erasmus+ KA1 Mobility of Youth Workers</p>
		<p>Stara Zagora · Bulgaria</p>
	</div>
</footer>

<style>
	:global(*) {
		box-sizing: border-box;
	}

	:global(html) {
		scroll-behavior: smooth;
	}

	:global(body) {
		margin: 0;
		background: #f3f0e7;
	}

	.page-header {
		--cream: #f3f0e7;
		--aqua: #48c8cb;

		position: absolute;
		top: 0;
		left: 0;
		z-index: 10;
		width: 100%;
		padding: 28px 32px;
	}

	.page-header__inner {
		display: flex;
		align-items: center;
		justify-content: space-between;
		width: min(1420px, 100%);
		margin-inline: auto;
	}

	.back-link {
		display: inline-flex;
		align-items: center;
		gap: 10px;
		color: rgba(243, 240, 231, 0.78);
		font-family: monospace;
		font-size: 0.7rem;
		letter-spacing: 0.13em;
		text-decoration: none;
		text-transform: uppercase;
		transition: color 200ms ease;
	}

	.back-link:hover {
		color: var(--aqua);
	}

	.back-link svg {
		width: 18px;
		height: 18px;
		fill: none;
		stroke: currentColor;
		stroke-width: 1.7;
		stroke-linecap: round;
		stroke-linejoin: round;
		transition: transform 200ms ease;
	}

	.back-link:hover svg {
		transform: translateX(-4px);
	}

	.project-name {
		color: var(--cream);
		font-family: Georgia, serif;
		font-size: 1.2rem;
		line-height: 0.9;
		text-align: right;
		text-decoration: none;
	}

	.project-name span,
	.project-name em {
		display: block;
	}

	.project-name em {
		margin-top: 5px;
		color: var(--aqua);
		font-weight: 400;
	}

	.hero {
		--cream: #f3f0e7;
		--forest: #123f37;
		--aqua: #48c8cb;
		--sage: #91a78e;
		--gold: #dca545;

		position: relative;
		min-height: 720px;
		padding: 180px 32px 120px;
		overflow: hidden;
		background-color: var(--forest);
		background-image:
			linear-gradient(rgba(72, 200, 203, 0.025) 1px, transparent 1px),
			linear-gradient(
				90deg,
				rgba(72, 200, 203, 0.025) 1px,
				transparent 1px
			);
		background-size: 56px 56px;
	}

	.hero::after {
		position: absolute;
		right: -12%;
		bottom: -260px;
		width: 700px;
		height: 700px;
		border: 1px solid rgba(72, 200, 203, 0.12);
		border-radius: 50%;
		content: "";
	}

	.hero__inner {
		position: relative;
		z-index: 2;
		width: min(1420px, 100%);
		margin-inline: auto;
	}

	.section-label {
		display: flex;
		align-items: center;
		gap: 14px;
		margin-bottom: 54px;
	}

	.section-label span {
		width: 34px;
		height: 1px;
		background: rgba(72, 200, 203, 0.7);
	}

	.section-label p {
		margin: 0;
		color: var(--sage);
		font-family: monospace;
		font-size: 0.68rem;
		letter-spacing: 0.17em;
		text-transform: uppercase;
	}

	.hero__content {
		display: grid;
		grid-template-columns: minmax(0, 1.25fr) minmax(300px, 0.55fr);
		gap: clamp(70px, 10vw, 170px);
		align-items: end;
	}

	.hero__eyebrow {
		margin: 0 0 28px;
		color: var(--aqua);
		font-family: monospace;
		font-size: 0.68rem;
		letter-spacing: 0.16em;
		text-transform: uppercase;
	}

	h1 {
		max-width: 960px;
		margin: 0;
		color: var(--cream);
		font-family: Georgia, serif;
		font-size: clamp(4rem, 7vw, 7.4rem);
		font-weight: 400;
		letter-spacing: -0.06em;
		line-height: 0.88;
	}

	h1 em {
		display: block;
		margin-top: 14px;
		color: var(--gold);
		font-weight: 400;
	}

	.hero__introduction {
		padding-bottom: 10px;
	}

	.hero__introduction p {
		margin: 0;
		color: rgba(243, 240, 231, 0.7);
		font-size: 1.05rem;
		line-height: 1.75;
	}

	.hero__introduction p + p {
		margin-top: 22px;
		color: var(--sage);
	}

	.hero__decoration {
		position: absolute;
		border-radius: 999px;
		pointer-events: none;
	}

	.hero__decoration--one {
		top: 150px;
		right: 7%;
		width: 100px;
		height: 270px;
		border: 1px solid rgba(72, 200, 203, 0.16);
		transform: rotate(32deg);
	}

	.hero__decoration--two {
		right: 23%;
		bottom: 65px;
		width: 44px;
		height: 170px;
		background: rgba(220, 165, 69, 0.08);
		transform: rotate(42deg);
	}

	.community {
		--cream: #f3f0e7;
		--forest: #123f37;
		--gold: #dca545;
		--grey: #5b6561;

		padding: clamp(100px, 12vw, 170px) 32px;
		background: var(--cream);
	}

	.community__inner {
		width: min(1420px, 100%);
		margin-inline: auto;
	}

	.country,
	.team-section {
		scroll-margin-top: 40px;
	}

	.country + .country,
	.team-section + .country {
		margin-top: clamp(100px, 12vw, 170px);
	}

	.group-header {
		display: grid;
		grid-template-columns: 70px 1fr auto;
		gap: 26px;
		align-items: end;
		margin-bottom: 42px;
		padding-bottom: 24px;
		border-bottom: 1px solid rgba(18, 63, 55, 0.16);
	}

	.group-header__number {
		color: rgba(18, 63, 55, 0.36);
		font-family: monospace;
		font-size: 0.72rem;
		letter-spacing: 0.16em;
	}

	.group-header__title p {
		margin: 0 0 7px;
		color: var(--gold);
		font-family: monospace;
		font-size: 0.68rem;
		letter-spacing: 0.17em;
		text-transform: uppercase;
	}

	.group-header__title h2 {
		margin: 0;
		color: var(--forest);
		font-family: Georgia, serif;
		font-size: clamp(2.5rem, 4vw, 4.7rem);
		font-weight: 400;
		letter-spacing: -0.045em;
		line-height: 0.96;
	}

	.group-header__count {
		margin: 0 0 7px;
		color: var(--grey);
		font-family: monospace;
		font-size: 0.67rem;
		letter-spacing: 0.13em;
		text-transform: uppercase;
	}

	.people-grid {
		display: grid;
		grid-template-columns: repeat(4, minmax(0, 1fr));
		gap: 22px;
	}

	.person {
		display: flex;
		align-items: center;
		gap: 18px;
		min-width: 0;
		padding: 18px;
		border: 1px solid rgba(18, 63, 55, 0.1);
		border-radius: 8px;
		background: rgba(255, 255, 255, 0.25);
		transition:
			transform 200ms ease,
			border-color 200ms ease,
			background 200ms ease;
	}

	.person:hover {
		transform: translateY(-3px);
		border-color: rgba(220, 165, 69, 0.42);
		background: rgba(255, 255, 255, 0.48);
	}

	.person__image {
		flex: 0 0 86px;
		width: 86px;
		height: 86px;
		overflow: hidden;
		border: 3px solid rgba(220, 165, 69, 0.25);
		border-radius: 50%;
		background:
			linear-gradient(
				145deg,
				rgba(145, 167, 142, 0.28),
				rgba(18, 63, 55, 0.14)
			);
	}

	.person__image img {
		display: block;
		width: 100%;
		height: 100%;
		object-fit: cover;
	}

	.person__content {
		min-width: 0;
	}

	.person__content h3 {
		margin: 0;
		color: var(--forest);
		font-family: Georgia, serif;
		font-size: 1.25rem;
		font-weight: 400;
		letter-spacing: -0.02em;
		line-height: 1.15;
	}

	.person__content p {
		margin: 7px 0 0;
		color: var(--gold);
		font-family: monospace;
		font-size: 0.61rem;
		letter-spacing: 0.13em;
		text-transform: uppercase;
	}

	.person__content span {
		display: block;
		margin-top: 7px;
		overflow: hidden;
		color: var(--grey);
		font-size: 0.82rem;
		line-height: 1.4;
		text-overflow: ellipsis;
		white-space: nowrap;
	}

	.closing {
		--forest: #123f37;
		--gold: #dca545;

		padding: clamp(110px, 13vw, 180px) 32px;
		background: #e5e5d9;
	}

	.closing__inner {
		width: min(1000px, 100%);
		margin-inline: auto;
		text-align: center;
	}

	.closing__small {
		margin: 0 0 28px;
		color: #587068;
		font-family: monospace;
		font-size: 0.69rem;
		letter-spacing: 0.17em;
		text-transform: uppercase;
	}

	.closing h2 {
		margin: 0;
		color: var(--forest);
		font-family: Georgia, serif;
		font-size: clamp(3.6rem, 6vw, 6.5rem);
		font-weight: 400;
		letter-spacing: -0.055em;
		line-height: 0.9;
	}

	.closing h2 em {
		display: block;
		margin-top: 12px;
		color: var(--gold);
		font-weight: 400;
	}

	.closing a {
		display: inline-flex;
		align-items: center;
		gap: 16px;
		margin-top: 52px;
		padding-bottom: 8px;
		border-bottom: 1px solid rgba(18, 63, 55, 0.34);
		color: var(--forest);
		font-family: monospace;
		font-size: 0.7rem;
		letter-spacing: 0.14em;
		text-decoration: none;
		text-transform: uppercase;
		transition:
			color 200ms ease,
			border-color 200ms ease;
	}

	.closing a:hover {
		border-color: var(--gold);
		color: var(--gold);
	}

	.closing a svg {
		width: 19px;
		height: 19px;
		fill: none;
		stroke: currentColor;
		stroke-width: 1.7;
		stroke-linecap: round;
		stroke-linejoin: round;
		transition: transform 200ms ease;
	}

	.closing a:hover svg {
		transform: translateX(5px);
	}

	.footer {
		padding: 32px;
		background: #123f37;
	}

	.footer__inner {
		display: flex;
		align-items: center;
		justify-content: space-between;
		gap: 30px;
		width: min(1420px, 100%);
		margin-inline: auto;
	}

	.footer p {
		margin: 0;
		color: rgba(145, 167, 142, 0.82);
		font-family: monospace;
		font-size: 0.62rem;
		letter-spacing: 0.15em;
		line-height: 1.6;
		text-transform: uppercase;
	}

	@media (max-width: 1150px) {
		.people-grid {
			grid-template-columns: repeat(3, minmax(0, 1fr));
		}
	}

	@media (max-width: 900px) {
		.hero {
			min-height: auto;
		}

		.hero__content {
			grid-template-columns: 1fr;
			gap: 60px;
		}

		.hero__introduction {
			max-width: 620px;
		}

		.people-grid {
			grid-template-columns: repeat(2, minmax(0, 1fr));
		}
	}

	@media (max-width: 600px) {
		.page-header {
			padding: 22px 20px;
		}

		.project-name {
			font-size: 1.05rem;
		}

		.back-link span {
			display: none;
		}

		.hero {
			padding: 145px 20px 90px;
		}

		.section-label {
			margin-bottom: 38px;
		}

		h1 {
			font-size: clamp(3.6rem, 16vw, 5.2rem);
		}

		.community {
			padding-inline: 20px;
		}

		.group-header {
			grid-template-columns: 40px 1fr;
			gap: 16px;
		}

		.group-header__count {
			grid-column: 2;
			margin-top: -7px;
		}

		.people-grid {
			grid-template-columns: 1fr;
			gap: 14px;
		}

		.person {
			padding: 15px;
		}

		.person__image {
			flex-basis: 74px;
			width: 74px;
			height: 74px;
		}

		.person__content h3 {
			font-size: 1.15rem;
		}

		.closing {
			padding-inline: 20px;
		}

		.closing h2 {
			font-size: clamp(3.3rem, 15vw, 4.8rem);
		}

		.footer {
			padding-inline: 20px;
		}

		.footer__inner {
			align-items: flex-start;
			flex-direction: column;
			gap: 12px;
		}
	}
</style>
