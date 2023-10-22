<script setup></script>

<template>
	<div class="techno__pill">
		<p class="techno__text accent"><slot>Vue JS</slot></p>
	</div>
</template>

<style lang="scss" scoped>
	@use "@/assets/styles/variables.scss" as v;

	.techno__pill {
		border-radius: 50px;
		border: solid 1px v.$accent-color;

		width: fit-content;
		padding: 5px 25px;

		user-select: none;
		background: none;
	}
</style>
