<script setup>
	import { ref, onMounted } from "vue";

	import VanillaTilt from "vanilla-tilt";
	import SkillItem from "./SkillItem.vue";

	const skillCard = ref(null);

	onMounted(() => {
		VanillaTilt.init(skillCard.value, {
			max: 5,
			speed: 400,
			glare: true,
			"max-glare": 0.1,
			scale: 1.02,
		});
	});

	import htmlIcon from "/src/assets/icons/html.svg";
	import cssIcon from "/src/assets/icons/css.svg";
	import jsIcon from "/src/assets/icons/javascript.svg";
	import vueIcon from "/src/assets/icons/vue.svg";
</script>

<template>
	<div class="skill__wrapper" ref="skillCard">
		<h4 class="skill__title">
			<slot name="skills-category-title">Front-end</slot>
		</h4>

		<ul class="skill__list">
			<slot name="skills-list">
				<SkillItem :iconUrl="htmlIcon">HTML</SkillItem>
				<SkillItem :iconUrl="cssIcon">Css</SkillItem>
				<SkillItem :iconUrl="jsIcon">JavaScript</SkillItem>
				<SkillItem :isImportant="true" :iconUrl="vueIcon">
					VueJS
				</SkillItem>
			</slot>
		</ul>
	</div>
</template>

<style lang="scss" scoped>
	@use "@/assets/styles/variables.scss" as v;

	.skill {
		&__wrapper {
			display: flex;
			flex-direction: column;
			justify-content: flex-start;
			align-items: flex-start;

			height: fit-content;
			width: 200px;
			padding: 25px;

			background: none;
			backdrop-filter: blur(0.8px);
			-webkit-backdrop-filter: blur(0.8px);
			border-radius: 10px;
			border: 1px solid rgba(255, 255, 255, 0.08);
		}

		&__title {
			text-align: center;
			width: 100%;
			margin-bottom: 25px;
		}

		&__list {
			display: flex;
			flex-direction: column;
			justify-content: flex-start;
			align-items: flex-start;
			gap: 15px;
		}
	}
</style>
