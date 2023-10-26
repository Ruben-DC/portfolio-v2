<script setup></script>

<template>
	<div class="cool-borders">
		<slot></slot>
	</div>
</template>

<style lang="scss" scoped>
	@use "@/assets/styles/variables.scss" as v;

	.cool-borders {
		height: fit-content;

		background: linear-gradient(
					to right,
					v.$primary-color 1px,
					transparent 1px
				)
				0 0,
			linear-gradient(to right, v.$primary-color 1px, transparent 1px) 0
				100%,
			linear-gradient(to left, v.$primary-color 1px, transparent 1px) 100%
				0,
			linear-gradient(to left, v.$primary-color 1px, transparent 1px) 100%
				100%,
			linear-gradient(to bottom, v.$primary-color 1px, transparent 1px) 0
				0,
			linear-gradient(to bottom, v.$primary-color 1px, transparent 1px)
				100% 0,
			linear-gradient(to top, v.$primary-color 1px, transparent 1px) 0
				100%,
			linear-gradient(to top, v.$primary-color 1px, transparent 1px) 100%
				100%;

		background-repeat: no-repeat;
		height: 100%;
	}

	.skills-card {
		background-size: 40px 60px;
	}

	.project-card {
		background-size: 70px 40px;
	}

	.contact-button {
		background-size: 10px 10px;
	}
</style>
