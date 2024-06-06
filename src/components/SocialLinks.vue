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
});
</script>

<template>
	<button
		class="social"
		type="button"
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
	width: 37px;
	height: 37px;
	background-color: white;
	border: none;
	border-radius: 12px;
	box-shadow: 0 4px 4px 0 rgba(0, 0, 0, 0.17);
	background-color: #90c1bf;
	padding: 4px;
	cursor: pointer;

	&:not(:first-child) {
		margin-left: 17px;
	}

	&:hover {
		box-shadow: 0 4px 4px 0 rgba(0, 0, 0, 0.37);
	}

	&:active {
		opacity: 0.8;
	}

	&::after {
		content: "";
		display: block;
		mask: var(--icon);
		mask-repeat: no-repeat;
		width: 29px;
		height: 29px;
		mask-size: 100%;
		background-color: #ffffff;
		mask-position: 50% 50%;
	}
}
</style>
