<script setup>
import {
	footerItems,
	footerItemsSecond,
	footerItemsThird,
} from '@/data/footer-items.js';
import SocialLinks from './SocialLinks.vue';
</script>

<template>
	<div class="nav">
		<ul class="nav__list">
			<li class="nav__item" v-for="item in footerItems" :key="item">
				<a class="nav__link" :href="item.url">{{ item.title }}</a>
			</li>
		</ul>
		<ul class="nav__list">
			<li class="nav__item" v-for="item in footerItemsSecond" :key="item">
				<a class="nav__link" :href="item.url">{{ item.title }}</a>
			</li>
		</ul>
		<ul class="nav__list">
			<li class="nav__item" v-for="item in footerItemsThird" :key="item">
				<a class="nav__link" :href="item.url">{{ item.title }}</a>
			</li>
		</ul>
		<div class="nav__social">
			<SocialLinks icon="inst" url="#!" size="medium">Инстаграмм</SocialLinks>
			<SocialLinks icon="whatsapp" url="#!" size="medium">Whatsapp</SocialLinks>
			<SocialLinks icon="call" url="#!" size="medium">Звонок</SocialLinks>
			<SocialLinks icon="telegram" url="#!" size="medium">Телеграм</SocialLinks>
		</div>
	</div>
</template>

<style scoped lang="scss">
.nav {
	position: relative;
	display: grid;
	grid-template-columns: 170px 157px 200px;
	gap: 42px;
}

.nav__list {
	margin: 0;
	padding: 0;
	list-style-type: none;
}

.nav__item {
	margin-bottom: 16px;
}

.nav__link {
	font-size: 16px;
	color: #fafaf9;
	text-decoration: none;

	&:hover {
		font-weight: 700;
	}

	&:active {
		opacity: 0.8;
	}
}

.nav__social {
	position: absolute;
	right: 24px;
	bottom: 19px;
}
</style>
