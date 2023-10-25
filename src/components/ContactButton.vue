<script setup>
	import CoolBorders from "./CoolBorders.vue";

	const props = defineProps({
		url: {
			type: String,
			default: "#projects",
		},

		icon: {
			type: String,
			default: "",
		},
	});
</script>

<template>
	<a :href="props.url" class="button">
		<button class="button__icon__wrapper">
			<CoolBorders class="button__icon__borders contact-button">
				<img class="button__icon" :src="props.icon" alt="icon" />
			</CoolBorders>
		</button>
		<p class="button__text"><slot>Git Hub</slot></p>
	</a>
</template>

<style lang="scss" scoped>
	@use "@/assets/styles/variables.scss" as v;

	.button {
		display: flex;
		flex-direction: row;
		align-items: center;

		height: fit-content;
		width: fit-content;

		&:hover {
			.button {
				&__icon__borders {
					width: 80%;
					height: 80%;

					color: v.$accent-color;

					/* Filtre pour passer de #dcdcdc à #f25959 */
					filter: invert(52%) sepia(95%) saturate(2076%)
						hue-rotate(326deg) brightness(99%) contrast(91%);

					@include v.mouse-enter-transition;
				}

				&__icon {
					width: 16px;
					height: 16px;
					@include v.mouse-enter-transition;
				}

				&__text {
					@include v.mouse-enter-transition;

					&::before {
						height: 16px;
						@include v.mouse-enter-transition;
					}
				}
			}
		}

		&__icon {
			width: 20px;
			height: 20px;

			@include v.mouse-leave-transition;

			&__wrapper {
				position: relative;
				display: flex;
				justify-content: center;
				align-items: center;

				width: 50px;
				height: 50px;

				margin-right: 20px;
			}

			&__borders {
				display: flex;
				justify-content: center;
				align-items: center;

				width: 100%;
				height: 100%;

				@include v.mouse-leave-transition;
			}
		}

		&__text {
			position: relative;
			@include v.mouse-leave-transition;

			&::before {
				content: "";
				position: absolute;
				bottom: -3px;
				z-index: -1;
				width: 103%;
				height: 2px;
				background-color: v.$accent-color;
				@include v.mouse-leave-transition;
			}
		}
	}
</style>
