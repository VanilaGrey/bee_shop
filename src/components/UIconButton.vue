<script setup>
defineProps({
	icon: {
		type: String,
		required: true,
	},
	count: {
		type: Number,
		default: null,
	},
});
</script>

<template>
	<button
		class="icon-button"
		type="button"
		:style="{ '--icon': `var(--icon-${icon})` }"
	>
		<span v-if="$slots.default" class="visually-hidden">
			<slot></slot>
		</span>
		<span v-if="count !== null" class="icon-button__count">{{ count }}</span>
	</button>
</template>

<style scoped lang="scss">
.icon-button {
	position: relative;
	width: 45px;
	height: 46px;
	background-color: white;
	border: none;
	border-radius: 12px;

	&::after {
		content: '';
		display: block;
		mask: var(--icon);
		mask-repeat: no-repeat;
		width: 32px;
		height: 37px;
		mask-size: 100%;
		background-color: #f2b236;
	}
}

.icon-button__count {
	position: absolute;
	top: 5px;
	right: 3px;
	z-index: 2;
	display: flex;
	justify-content: center;
	align-items: center;
	width: 14px;
	height: 14px;
	font-weight: 500;
	font-size: 10px;
	color: white;
	background-color: #db4e66;
	border-radius: 50%;
}
</style>
