<script setup>
defineProps({
	icon: {
		type: String,
		required: true,
	},
	placeholder: String,
	type: {
		type: String,
		default: 'text',
		validator: (val) => ['text', 'password', 'search', 'email', 'tel', 'textarea'].includes(val),
	},
});
</script>
<template>
	<input
		v-if="type !== 'textarea'"
		class="form__input"
		:type="type"
		:placeholder="placeholder"
	/>
	<textarea
		v-else
		class="form__input"
		type="text"
		rows="3"
		:placeholder="placeholder"
	/>
</template>

<style scoped lang="scss">
.form__input {
	position: relative;
	box-sizing: border-box;
	width: 100%;
	padding: 14px 50px 14px 22px;
	border: none;
	outline: none;
}
</style>
