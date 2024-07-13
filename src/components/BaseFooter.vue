<script setup>
import Logo from './BaseLogo.vue';
import UInput from './UInput.vue';
import PrivacyPolicy from './PrivacyPolicy.vue';
import FooterLinks from './FooterLinks.vue';
</script>

<template>
	<footer class="footer">
		<div class="footer__inner container">
			<div class="footer__top">
				<div>
					<logo class="footer__logo" />
					<span class="footer__contacts">
					<a href="tel:+70000000000">8(000) 000 00 00 </a
					>МСК (9-21)</span
					><br />
					<a class="footer__contacts" href="mailto:pchelkashop.ru@mail.ru"
						>pchelkashop.ru@mail.ru</a
					>
				</div>
				<div class="footer__input">
					<UInput
						class="footer__input--controll"
						placeholder="Поиск по сайту...."
					/>
				</div>
			</div>
			<div>
				<FooterLinks />
			</div>
		</div>
	</footer>

	<PrivacyPolicy />
</template>

<style scoped lang="scss">
.footer {
	z-index: 1;
	padding-top: 58px;
	padding-bottom: 70px;
	background: linear-gradient(167deg, #f2b236 0%, #ff9c1a 100%);
}

.footer__inner {
	display: grid;
	grid-template-columns: 290px 1fr;
	gap: 299px;
}

.footer__top {
	margin-left: 24px;
}

.footer__logo {
	width: 265px;
	margin: 0;
	margin-bottom: 15px;
}

.footer__contacts {
	margin: 0;
	padding: 0;
	font-weight: 500;
	font-size: 18px;
	color: #884900;
}

.footer__input {
	position: relative;
	width: 265px;
	margin-top: 41px;

	&::before {
		content: '';
		position: absolute;
		top: 13px;
		right: 16px;
		z-index: 2;
		display: block;
		width: 19px;
		height: 19px;
		background-color: #a5aaaf;
		cursor: pointer;
		mask-image: var(--icon-search);
		mask-repeat: no-repeat;
		mask-size: 100%;
	}

	&--controll {
		font-weight: 400;
		font-size: 16px;
		border-radius: 26px;
	}
}
</style>
