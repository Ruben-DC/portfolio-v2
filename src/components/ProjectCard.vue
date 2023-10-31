<script setup>
	import { ref, onMounted } from "vue";
	import VanillaTilt from "vanilla-tilt";

	const card = ref(null);

	onMounted(() => {
		VanillaTilt.init(card.value, {
			max: 5,
			speed: 400,
			glare: true,
			"max-glare": 0.1,
			scale: 1.02,
		});
	});

	const props = defineProps({
		url: {
			type: String,
			default: "#projects",
		},
	});

	import linkIcon from "/src/assets/icons/link.svg";
</script>

<template>
	<div class="project__wrapper" ref="card">
		<a class="project__title__link" :href="props.url">
			<h3 class="project__title">
				<slot name="title">Titre du projet</slot>

				<span
					class="project__project-link__icon"
					v-if="props.url !== '#projects'"
				>
					<img :src="linkIcon" alt="link icon" />
				</span>
			</h3>
		</a>

		<p class="project__description caption">
			<slot name="description">
				Lorem ipsum dolor sit amet consectetur adipisicing elit.
				Quisquam quibusdam, voluptatum, quod, quia voluptatem voluptas
				quos asperiores quae voluptatibus doloribus quas.
			</slot>
		</p>

		<div class="project__details">
			<slot name="technos">
				<TechnoPill>Vue JS</TechnoPill>
				<TechnoPill>Express JS</TechnoPill>
			</slot>
		</div>
	</div>
</template>

<style lang="scss" scoped>
	@use "@/assets/styles/variables.scss" as v;

	.project {
		&__wrapper {
			display: flex;
			flex-direction: column;
			justify-content: flex-start;
			align-items: flex-start;
			gap: 15px;

			width: 100%;
			height: fit-content;
			padding: 25px;
			margin-bottom: 15px;

			background: none;
			backdrop-filter: blur(0.8px);
			-webkit-backdrop-filter: blur(0.8px);
			border-radius: 10px;
			border: 1px solid rgba(255, 255, 255, 0.08);
		}

		&__title {
			display: flex;
			flex-direction: row;
			justify-content: flex-start;
			align-items: center;
			gap: 15px;
		}

		&__description {
			width: 100%;
			max-width: 500px;
		}

		&__details {
			display: flex;
			flex-direction: row;
			justify-content: flex-start;
			flex-wrap: wrap;

			gap: 15px;
			width: 100%;
		}
	}
</style>
