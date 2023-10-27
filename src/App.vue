<script setup>
	import SkillCard from "./components/SkillCard.vue";
	import ProjectCard from "@/components/ProjectCard.vue";
	import TechnoPill from "@/components/TechnoPill.vue";
	import CoolButton from "@/components/CoolButton.vue";

	import htmlIcon from "/src/assets/icons/html.svg";
	import cssIcon from "/src/assets/icons/css.svg";
	import scssIcon from "/src/assets/icons/scss.svg";
	import jsIcon from "/src/assets/icons/javascript.svg";
	import vueIcon from "/src/assets/icons/vue.svg";
	import reactIcon from "/src/assets/icons/react.svg";

	import githubIcon from "/src/assets/icons/github.svg";
	import figmaIcon from "/src/assets/icons/figma.svg";
	import xdIcon from "/src/assets/icons/xd.svg";

	import contactMeIcon from "/src/assets/icons/contact-me.svg";
	import projectIcon from "/src/assets/icons/project.svg";
	import linkedinIcon from "/src/assets/icons/linkedin.svg";
	import mailIcon from "/src/assets/icons/email.svg";
	import devtoIcon from "/src/assets/icons/devto.svg";
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

				<div class="cta-buttons">
					<CoolButton
						:icon="contactMeIcon"
						url="#contact"
						target="_self"
					>
						Me contacter
					</CoolButton>

					<CoolButton
						:icon="projectIcon"
						url="#projects"
						target="_self"
					>
						Mes projets
					</CoolButton>
				</div>
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

		<section id="skills">
			<h2><a href="#skills">Mes compétences</a></h2>

			<div class="skills-categories-wrapper">
				<SkillCard>
					<template #skills-category-title> Front-end </template>

					<template #skills-list>
						<li>
							<span class="skill-icon">
								<img :src="htmlIcon" alt="icone html" />
							</span>

							HTML
						</li>

						<li class="important-skill">
							<span class="skill-icon">
								<img :src="scssIcon" alt="icone sass" />
							</span>

							SCSS
						</li>

						<li>
							<span class="skill-icon">
								<img :src="jsIcon" alt="icone javascript" />
							</span>

							Javascript
						</li>

						<li class="important-skill">
							<span class="skill-icon">
								<img :src="vueIcon" alt="Icone VueJS" />
							</span>

							VueJS
						</li>
					</template>
				</SkillCard>

				<SkillCard>
					<template #skills-category-title> Autres </template>

					<template #skills-list>
						<li>
							<span class="skill-icon"
								><img
									:src="githubIcon"
									alt="icone Github" /></span
							>GitHub
						</li>
						<li>
							<span class="skill-icon"
								><img :src="figmaIcon" alt="" /></span
							>Figma
						</li>
						<li>
							<span class="skill-icon"
								><img :src="xdIcon" alt="" /></span
							>AdobeXd
						</li>
					</template>
				</SkillCard>
			</div>
		</section>

		<section id="projects">
			<h2><a href="#projects">Mes projets</a></h2>

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
			<h2><a href="#contact">Me contacter</a></h2>

			<div class="contact-buttons">
				<CoolButton
					:icon="mailIcon"
					url="mailto:contact@rudendc.fr"
					target="_self"
				>
					contact@rubenc.fr
				</CoolButton>

				<CoolButton
					:icon="githubIcon"
					url="https://github.com/Ruben-DC"
				>
					github.com/Ruben-DC
				</CoolButton>

				<CoolButton
					:icon="linkedinIcon"
					url="https://www.linkedin.com/in/rub%C3%A9n-de-carvalho-327a5b278"
				>
					linkedin.com/in/Ruben-DC
				</CoolButton>

				<CoolButton :icon="devtoIcon" url="https://dev.to/rubendc">
					dev.to/rubendc
				</CoolButton>
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
		z-index: 1000;
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
			z-index: 500;
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

		.cta-buttons {
			display: flex;
			flex-direction: row;
			flex-wrap: wrap;
			row-gap: 20px;
			column-gap: 50px;
		}
	}

	#skills {
		height: fit-content;

		margin-bottom: 170px;

		.skills-categories-wrapper {
			display: flex;
			flex-direction: row;
			align-items: flex-start;
			flex-wrap: wrap;
			gap: 70px;
		}

		.skill__card {
			li {
				display: flex;
				flex-direction: row;
				flex-wrap: nowrap;
				gap: 10px;
			}

			li.important-skill {
				color: v.$accent-color;

				background: -webkit-linear-gradient(
					0deg,
					v.$accent-color 25%,
					v.$third-blob-color 100%
				);
				-webkit-background-clip: text;
				-webkit-text-fill-color: transparent;

				.skill-icon {
					/* Filtre pour passer de #dcdcdc à #f25959 */
					filter: invert(52%) sepia(95%) saturate(2076%)
						hue-rotate(326deg) brightness(99%) contrast(91%);
				}
			}

			.skill-icon img {
				height: v.$p-font-size;
				width: v.$p-font-size;
			}
		}
	}

	#projects {
		height: fit-content;
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
				flex-direction: column;
				justify-content: center;
				align-items: center;

				height: 100%;
				width: 100%;
				overflow-x: hidden;
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
		}

		.contact-button {
			margin-right: 20px;
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
	}

	@media screen and (max-width: v.$breakpoint-mobile) {
		#home {
			.blob-container {
				display: none;
			}
		}

		#skills {
			.skills-categories-wrapper {
				width: 100%;
				flex-direction: column;
				// justify-content: center;
				align-items: center;
			}
		}

		#projects {
			.carousel {
				padding-bottom: 5px;
			}
		}
	}
</style>
