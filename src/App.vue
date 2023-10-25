<script setup>
	import ProjectCard from "@/components/ProjectCard.vue";
	import TechnoPill from "@/components/TechnoPill.vue";
	import ContactButton from "@/components/ContactButton.vue";

	const githubIcon = "/src/assets/icons/github.svg";
	const linkedinIcon = "/src/assets/icons/linkedin.svg";
	const mailIcon = "/src/assets/icons/email.svg";
	const devtoIcon = "/src/assets/icons/devto.svg";
</script>

<template>
	<header>
		<a href="#home"><p>rubendc.fr</p></a>

		<a href="mailto:contact@rubendc.fr"><p>Me contacter</p></a>
	</header>

	<main>
		<section id="home">
			<div class="presentation">
				<h1>
					Salut ! <br />
					Je suis <span class="accent">Rubén</span>
				</h1>

				<p>
					Apprenti développeur web front-end. Je travaille avec Figma,
					HTML, CSS, Javascript et même le framework
					<span class="accent">VueJS</span>.
				</p>

				<div class="action-buttons"></div>
			</div>

			<div class="decoration">
				<div class="blob-container">
					<div class="first blob"></div>
					<div class="second blob"></div>
					<div class="third blob"></div>
				</div>

				<img src="./assets/img/memoji.png" alt="Rubén" id="me" />
			</div>
		</section>

		<section id="competences">
			<h2>Mes compétences</h2>
		</section>

		<section id="projects">
			<h2>Mes projets</h2>

			<div class="carousel">
				<ProjectCard>
					<template #title> 🎥 Cinémotion </template>

					<template #description>
						Cinemotion est une application front-end où les
						passionnés de cinéma peuvent créer des listes
						personnalisées de leurs films et séries préférés.
					</template>

					<template #technos>
						<TechnoPill>Vue JS</TechnoPill>
						<TechnoPill>API</TechnoPill>
					</template>
				</ProjectCard>

				<ProjectCard>
					<template #title> 💭 Homttchat </template>

					<template #description>
						Homttchat est une application de chat en ligne où les
						utilisateurs peuvent discuter en temps réel avec
						d'autres utilisateurs.
					</template>

					<template #technos>
						<TechnoPill>Vue JS</TechnoPill>
						<TechnoPill>Express JS</TechnoPill>
						<TechnoPill>Socket IO</TechnoPill>
					</template>
				</ProjectCard>
			</div>
		</section>

		<section id="contact">
			<h2>Me contacter</h2>

			<div class="contact-buttons">
				<ContactButton :icon="mailIcon" url="mailto:contact@rudendc.fr">
					contact@rubenc.fr
				</ContactButton>

				<ContactButton
					:icon="githubIcon"
					url="https://github.com/Ruben-DC"
					target="_blank"
				>
					github.com/Ruben-DC
				</ContactButton>

				<ContactButton
					:icon="linkedinIcon"
					url="https://www.linkedin.com/in/rub%C3%A9n-de-carvalho-327a5b278"
					target="_blank"
				>
					linkedin.com/in/Ruben-DC
				</ContactButton>

				<ContactButton
					:icon="devtoIcon"
					url="https://dev.to/rubendc"
					target="_blank"
				>
					dev.to/rubendc
				</ContactButton>
			</div>
		</section>
	</main>

	<footer>
		<a href="#home">
			<p>Rubén De Carvalho</p>
		</a>

		<div class="details">
			<p>Créé avec VueJS</p>

			<p>Designé avec Figma</p>
		</div>
	</footer>
</template>

<style lang="scss" scoped>
	@use "@/assets/styles/variables.scss" as v;

	header {
		position: fixed;
		top: 0;
		left: 0;

		display: flex;
		flex-direction: row;
		justify-content: space-between;
		align-items: center;

		width: 100%;
		height: 80px;

		padding: 0 40px;

		p {
			font-size: 12px;
			color: v.$text-color-secondary;
			transition: all 0.2s ease-in-out;

			&:hover {
				color: v.$text-color;
			}
		}
	}

	section {
		display: flex;
		flex-direction: column;
		justify-content: center;

		width: 100%;

		h2 {
			margin-bottom: 60px;
		}
	}

	#home {
		position: relative;
		flex-direction: row;
		justify-content: space-between;
		align-items: center;

		.presentation {
			z-index: 1000;
			position: absolute;

			display: flex;
			flex-direction: column;
			gap: 25px;
			max-width: 500px;
			width: 100%;
		}

		.decoration {
			position: absolute;
			top: 0;
			right: 0;

			display: flex;
			flex-direction: column;
			justify-content: center;
			align-items: center;

			max-width: 500px;
			width: 100%;
			height: 100%;

			.blob-container {
				top: 50%;
				right: 0;
				transform: translateY(-50%);

				.first {
					top: 300px;
					height: 250px;

					animation: first 8s infinite linear;
				}

				.second {
					top: 200px;
					left: 100px;

					animation: second 8s infinite ease;
				}
				.third {
					opacity: 0.8;

					top: 80px;
					right: -20px;

					animation: second 8s infinite ease;
				}
			}

			#me {
				position: absolute;
				right: 0;

				width: 250px;

				transform: rotate(10deg);
				@include v.mouse-leave-transition;

				&:hover {
					transform: rotate(-2deg) scale(1.05);
					@include v.mouse-enter-transition;
				}
			}
		}
	}

	#projects {
		.carousel {
			display: grid;
			grid-auto-flow: column;
			grid-auto-columns: 555px;
			align-items: center;
			gap: 35px;

			height: 400px;

			overflow-x: scroll;
			overflow-y: hidden;

			@media screen and (max-width: v.$breakpoint-mobile) {
				display: flex;
				height: auto;
			}
		}
	}

	#contact {
		.contact-buttons {
			display: flex;
			flex-direction: row;

			column-gap: 150px;
			row-gap: 45px;

			align-items: center;
			flex-wrap: wrap;

			// @media screen and (max-width: v.$breakpoint-tablet) {
			// 	flex-direction: column;
			// 	column-gap: normal;
			// 	align-items: flex-start;
			// 	justify-content: center;
			// }
		}

		.contact-button {
			margin-right: 20px;
			// @media screen and (max-width: v.$breakpoint-mobile) {
			// 	margin-right: 0;
			// }
		}
	}

	footer {
		display: flex;
		flex-direction: row;
		justify-content: space-between;
		align-items: center;

		width: 100%;
		height: 80px;
		border-top: 1px solid v.$text-color-secondary;

		padding: 0 10px;

		p {
			font-size: 12px;
			color: v.$text-color-secondary;
			transition: all 0.2s ease-in-out;
			text-wrap: wrap;
			text-overflow: ellipsis;

			&:hover {
				color: v.$text-color;
			}
		}

		.details {
			display: flex;
			flex-direction: row;
			gap: 20px;
			user-select: none;

			p:hover {
				color: v.$accent-color;
			}
		}
	}

	@media screen and (max-width: v.$breakpoint-tablet) {
		#home {
			flex-direction: column;
			justify-content: center;
			align-items: center;

			.decoration {
				height: 50%;

				#me {
					order: -1;

					bottom: 10%;
					width: 200px;
				}
			}
		}

		// #projects {
		// 	.carousel {
		// 		padding-bottom: 5px;
		// 	}
		// }
	}

	@media screen and (max-width: v.$breakpoint-mobile) {
		#home {
			.blob-container {
				display: none;
			}
		}

		#projects {
			.carousel {
				padding-bottom: 5px;
			}
		}
	}
</style>
