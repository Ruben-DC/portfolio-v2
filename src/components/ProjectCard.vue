<script setup>
	import { ref } from "vue";
	import TechnoPill from "./TechnoPill.vue";
	import CoolBorders from "./CoolBorders.vue";

	const props = defineProps({
		url: {
			type: String,
			default: "#projects",
		},
	});
</script>

<template>
	<div class="project__wrapper">
		<CoolBorders class="project-card">
			<div class="project__content">
				<h3 class="project__title">
					<a class="project__title__link" :href="props.url">
						<slot name="title">Titre du projet</slot>

						<span
							class="project__project-link__icon"
							v-if="props.url !== '#projects'"
						>
							<img src="" alt="link icon" />
						</span>
					</a>
				</h3>

				<p class="project__description caption">
					<slot name="description">
						Lorem ipsum dolor sit amet consectetur adipisicing elit.
						Quisquam quibusdam, voluptatum, quod, quia voluptatem
						voluptas quos asperiores quae voluptatibus doloribus
						quas.
					</slot>
				</p>

				<div class="project__details">
					<slot name="technos">
						<TechnoPill>Vue JS</TechnoPill>
						<TechnoPill>Express JS</TechnoPill>
					</slot>
				</div>
			</div>
		</CoolBorders>
	</div>
</template>

<style lang="scss" scoped>
	@use "@/assets/styles/variables.scss" as v;

	.project {
		&__wrapper {
			position: relative;
			display: flex;
			justify-content: center;
			align-items: center;

			max-width: 555px;
			width: 100%;
			height: fit-content;

			&:hover {
				.project__content {
					margin: 35px;
					@include v.mouse-enter-transition;
				}
			}
		}

		&__content {
			display: flex;
			flex-direction: column;
			gap: 25px;
			background: none;

			max-width: 411px;
			width: 100%;
			height: fit-content;
			margin: 50px 62px;

			@include v.mouse-leave-transition;
		}

		&__details {
			display: flex;
			flex-wrap: wrap;
			gap: 25px;
		}
	}

	@media screen and (max-width: v.$breakpoint-mobile) {
		.project {
			&__wrapper {
				width: 100%;
				height: fit-content;
			}

			&__content {
				margin: 45px 20px;
			}

			&__details {
				gap: 10px;
				width: 85%;
			}

			&__description {
				font-size: 0.9rem;
				width: 85%;
			}
		}
	}
</style>
