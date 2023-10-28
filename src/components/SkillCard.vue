<script setup>
	import CoolBorders from "./CoolBorders.vue";
	import SkillItem from "./SkillItem.vue";

	import htmlIcon from "/src/assets/icons/html.svg";
	import cssIcon from "/src/assets/icons/css.svg";
	import jsIcon from "/src/assets/icons/javascript.svg";
	import vueIcon from "/src/assets/icons/vue.svg";
</script>

<template>
	<CoolBorders class="skill__card skills-card">
		<div class="skill__content">
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
	</CoolBorders>
</template>

<style lang="scss" scoped>
	@use "@/assets/styles/variables.scss" as v;

	.skill {
		&__card {
			display: flex;
			flex-direction: column;
			justify-content: center;
			align-items: center;

			min-width: 220px;
			width: fit-content;

			height: fit-content;

			padding: 40px;

			transition: all 0.2s ease-in-out;
			user-select: none;
		}

		&__title {
			margin-bottom: 25px;
		}

		&__list {
			display: flex;
			flex-direction: column;
			justify-content: center;
			gap: 15px;

			width: 100%;
			height: fit-content;
		}
	}
</style>
