<script setup>
	import { ref } from "vue";
	import TechnoPill from "./TechnoPill.vue";

	const props = defineProps({
		url: {
			type: String,
			default: "#projects",
		},
	});
</script>

<template>
	<div class="project__wrapper">
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

			<p class="project__description">
				<slot name="description">
					Lorem ipsum dolor sit amet consectetur adipisicing elit.
					Quisquam quibusdam, voluptatum, quod, quia voluptatem
					voluptas quos asperiores quae voluptatibus doloribus quas.
				</slot>
			</p>

			<div class="project__details">
				<slot name="technos">
					<TechnoPill>Vue JS</TechnoPill>
					<TechnoPill>Express JS</TechnoPill>
				</slot>
			</div>
		</div>
	</div>
</template>

<style lang="scss" scoped>
	@use "@/assets/styles/variables.scss" as v;

	.project {
		&__wrapper {
			height: fit-content;
			padding: 60px 72px;
			width: fit-content;

			background: linear-gradient(
						to right,
						v.$primary-color 1px,
						transparent 1px
					)
					0 0,
				linear-gradient(to right, v.$primary-color 1px, transparent 1px)
					0 100%,
				linear-gradient(to left, v.$primary-color 1px, transparent 1px)
					100% 0,
				linear-gradient(to left, v.$primary-color 1px, transparent 1px)
					100% 100%,
				linear-gradient(
						to bottom,
						v.$primary-color 1px,
						transparent 1px
					)
					0 0,
				linear-gradient(
						to bottom,
						v.$primary-color 1px,
						transparent 1px
					)
					100% 0,
				linear-gradient(to top, v.$primary-color 1px, transparent 1px) 0
					100%,
				linear-gradient(to top, v.$primary-color 1px, transparent 1px)
					100% 100%;
			background-repeat: no-repeat;
			background-size: 70px 40px;
		}

		&__content {
			display: flex;
			flex-direction: column;
			gap: 25px;

			width: 411px;
		}

		&__details {
			display: flex;
			flex-wrap: wrap;
			gap: 25px;
		}
	}
</style>
