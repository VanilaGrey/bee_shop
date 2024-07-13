<script setup>
import Logo from './BaseLogo.vue';
import UInput from './UInput.vue';
import UButton from './UIconButton.vue';
import MenuItem from './HeaderMenu.vue';
</script>

<template>
	<header class="header">
		<div class="header__inner container">
			<Logo />
			<div class="header__container">
				<span class="header__text">
					<a href="tel:+70000000000">8-(000)-000-00-00 </a>МСК (9-21)</span
				>
				<div class="header__input">
					<UInput
						class="header__input--controll"
						placeholder="Поиск по сайту..."
					/>
				</div>

				<UButton icon="basket"> Открыть корзину. </UButton>
				<UButton icon="profile"> Открыть профиль. </UButton>
			</div>
		</div>
	</header>
	<menu-item />
</template>

<style scoped lang="scss">
.header {
	z-index: 1;
	background: linear-gradient(167deg, #f2b236 0%, #ff9c1a 100%);
	box-shadow: 0 0 18px 0 #ffdba6;
}

.header__input {
	position: relative;
	width: 327px;

	&::before {
		content: '';
		position: absolute;
		top: 9px;
		right: 16px;
		z-index: 2;
		display: block;
		width: 24px;
		height: 24px;
		background-color: #a5aaaf;
		cursor: pointer;
		mask-image: var(--icon-search);
		mask-repeat: no-repeat;
		mask-size: 100%;
	}

	&--controll {
		border-radius: 26px;
	}
}

.header__inner {
	display: grid;
	align-items: center;
	grid-template-columns: 330px 1fr;
	padding-top: 42px;
	padding-bottom: 23px;
	gap: 93px;
}

.header__container {
	display: flex;
	align-items: center;
	gap: 25px;
	margin-top: -7px;
	padding-right: 21px;
}

.header__text {
	margin: 0;
	margin-top: 7px;
	padding: 0;
	font-weight: 500;
	font-size: 18px;
	color: #884900;
	letter-spacing: 0.5px;
}
</style>
