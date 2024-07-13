<script setup>
import UButton from './UButton.vue';
import SocialLinks from './SocialLinks.vue';
</script>

<template>
	<section class="preview">
		<img class="preview__image" src="/images/foto-1.jpg" alt="foto-preview" />
		<p class="preview__title">
			Квест в коробке – объединяет<br />
			семью и друзей в поисках разгадки
		</p>
		<p class="preview__description">
			Подготовка до 10 минут, прохождение 60-90 минут, яркие эмоции - надолго!
		</p>
		<UButton class="preview__button">выбрать игру </UButton>
		<div class="preview__social">
			<SocialLinks icon="inst-big" url="#!" size="large"
				>Инстаграмм</SocialLinks
			>
			<SocialLinks icon="whatsapp-big" url="#!" size="large"
				>Whatsapp</SocialLinks
			>
			<SocialLinks icon="call-big" url="#!" size="large">Звонок</SocialLinks>
			<SocialLinks icon="telegram-big" url="#!" size="large"
				>Телеграм</SocialLinks
			>
		</div>
	</section>
</template>

<style scoped lang="scss">
.preview {
	position: relative;
	display: flex;
	flex-direction: column;
	align-items: center;
	margin: 0;
	padding: 239px 100px 156px;
}

.preview__image {
	position: absolute;
	top: 0;
	z-index: -1;
	width: 100%;
	height: 100%;
	background-color: $white;
}

.preview__title {
	margin: 0 auto;
	font-weight: 500;
	font-size: 50px;
	line-height: 1.14;
	text-align: center;
	color: #fafaf9;
}

.preview__description {
	margin-top: 16px;
	margin-bottom: 43px;
	font-size: 16px;
}

.preview__button {
	width: 306px;
	color: $white;
	background-color: $red;
}

.preview__social {
	position: absolute;
	right: 138px;
	bottom: 34px;
}
</style>
