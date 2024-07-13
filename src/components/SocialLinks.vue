<script setup>
defineProps({
	icon: {
		type: String,
		required: true,
	},
	url: {
		type: String,
		required: true,
	},
	size: {
		type: String,
		default: 'medium',
	},
});
</script>

<template>
	<button
		class="social"
		type="button"
		:class="`social--${size}`"
		:style="{ '--icon': `var(--icon-${icon})` }"
	>
		<span v-if="$slots.default" class="visually-hidden">
			<slot></slot>
		</span>
	</button>
</template>

<style scoped lang="scss">
.social {
	position: relative;
	padding: 4px;
	background-color: #90c1bf;
	border: none;
	border-radius: 12px;
	box-shadow: 0 4px 4px 0 rgba(0, 0, 0, 0.17);
	cursor: pointer;

	&:not(:first-child) {
		margin-left: 22px;
	}

	&:hover {
		box-shadow: 0 4px 4px 0 rgba(0, 0, 0, 0.37);
	}

	&:active {
		opacity: 0.8;
	}

	&::after {
		content: '';
		display: block;
		mask: var(--icon);
		mask-repeat: no-repeat;
		background-color: #ffffff;
		mask-position: 50% 50%;
	}

	&--small {
		width: 25px;
		height: 25px;

		&::after {
			width: 20px;
			height: 20px;
		}
	}

	&--medium {
		width: 37px;
		height: 37px;

		&::after {
			width: 29px;
			height: 29px;
		}
	}

	&--large {
		width: 50px;
		height: 50px;

		&::after {
			width: 40px;
			height: 40px;
		}
	}
}
</style>
