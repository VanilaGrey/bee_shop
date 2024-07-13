<template>
	<div class="privacy">
		<div class="privacy__inner container">
			<div class="privacy__politic">
				<a class="privacy__text">Политика конфиденциальности</a>
				<a class="privacy__text">Публичная оферта</a>
			</div>
			<p class="privacy__text">Все права защищены 2021</p>
		</div>
	</div>
</template>

<style scoped lang="scss">
.privacy {
	display: flex;
	padding-top: 56px;
	padding-bottom: 56px;
	color: #ced0d2;
	background-color: #222528;
}

.privacy__inner {
	display: flex;
	justify-content: space-between;
	padding: 0 42px;
}

.privacy__politic {
	display: flex;
	gap: 52px;
}

.privacy__text {
	margin: 0;
	font-size: 16px;
	color: #ced0d2;
}
</style>
