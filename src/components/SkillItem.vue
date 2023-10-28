<script setup>
	const props = defineProps({
		isImportant: {
			type: Boolean,
			default: false,
		},

		iconUrl: {
			type: String,
			default: "",
		},
	});
</script>

<template>
	<li :class="{ important: isImportant }" class="skill__item">
		<span v-if="props.iconUrl" class="skill__icon">
			<img :src="props.iconUrl" alt="skill icon" />
		</span>

		<slot>Vue JS</slot>
	</li>
</template>

<style lang="scss" scoped>
	@use "@/assets/styles/variables.scss" as v;

	.skill {
		&__item {
			display: flex;
			flex-direction: row;
			flex-wrap: nowrap;
			// align-items: self-end;
			gap: 10px;
		}

		&__icon img {
			height: v.$p-font-size;
			width: v.$p-font-size;
		}
	}

	.important {
		color: v.$accent-color;

		background: -webkit-linear-gradient(
			0deg,
			v.$accent-color 25%,
			v.$third-blob-color 100%
		);
		background-clip: text;
		-webkit-background-clip: text;
		-webkit-text-fill-color: transparent;

		.skill__icon {
			/* Filtre pour passer de #dcdcdc à #f25959 */
			filter: invert(52%) sepia(95%) saturate(2076%) hue-rotate(326deg)
				brightness(99%) contrast(91%);
		}
	}
</style>
