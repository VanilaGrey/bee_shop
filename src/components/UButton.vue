<template>
	<button class="button">
		<slot />
	</button>
</template>

<style scoped lang="scss">
.button {
	width: 100%;
	padding: 18px;
	font-weight: 500;
	font-size: 16px;
	text-transform: uppercase;
	border: none;
	border-radius: 14px;
	box-shadow: 2px 4px 9px 0 rgba(243, 55, 87, 0.42);
}
</style>
