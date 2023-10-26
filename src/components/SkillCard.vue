<script setup>
	import CoolBorders from "./CoolBorders.vue";
</script>

<template>
	<CoolBorders class="skill__card skills-card">
		<div class="skill__content">
			<h4 class="skill__title">
				<slot name="skills-category-title">Front-end</slot>
			</h4>

			<ul class="skill__list">
				<slot name="skills-list">
					<li>HTML</li>
					<li>CSS</li>
					<li>Javascript</li>
					<li>VueJS</li>
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

			width: fit-content;
			height: fit-content;

			padding: 30px 40px;

			transition: all 0.2s ease-in-out;
			user-select: none;

			&:hover {
				// transform: scale(1.05);

				.skill__title {
					// color: v.$accent-color;
					// text-decoration: wavy underline v.$accent-color;
				}
			}
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

		li {
			font-size: 16px;
			font-weight: 400;
			list-style: square;
		}
	}
</style>
