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
		<CoolBorders>
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

			min-width: 555px;
			max-width: 555px;
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

			width: 411px;
			height: fit-content;
			margin: 60px 72px;

			@include v.mouse-leave-transition;
		}

		&__details {
			display: flex;
			flex-wrap: wrap;
			gap: 25px;
		}
	}
</style>
