<script setup>
import { clickOutside as vClickOutside } from 'v-click-outside-vue3';
import { ref } from 'vue';
import menuItems from '@/data/menu-items.js';

const categoryIndex = ref(-1);

const setCategoryIndex = (index = -1) => {
	categoryIndex.value = categoryIndex.value === index ? -1 : index;
};
</script>

<template>
	<nav class="menu container" v-click-outside="setCategoryIndex">
		<ul class="menu__list">
			<li
				class="menu__item"
				v-for="(item, index) in menuItems"
				:key="index"
				@click="setCategoryIndex(index)"
			>
				<a class="menu__link" :href="item.url">
					{{ item.title }}
				</a>
				<ul
					:class="{ menu__sublist: categoryIndex === index }"
					v-if="categoryIndex === index"
				>
					<li
						class="menu__subitem"
						v-for="(subitem, subindex) in item.subitems"
						:key="subindex"
					>
						<a class="menu__link" :href="subitem.url">{{ subitem.title }}</a>
					</li>
				</ul>
			</li>
		</ul>
	</nav>
</template>

<style scoped lang="scss">
.menu {
	position: relative;
}

.menu__list {
	display: flex;
	justify-content: flex-end;
	margin: 0;
	padding: 0;
	list-style-type: none;
}

.menu__item {
	padding: 22px 20px 21px 15px;
	cursor: pointer;

	&:hover {
		background-color: #f2b236;
		box-shadow: 0 4px 4px 0 rgba(0, 0, 0, 0.25);
	}

	&:active {
		opacity: 0.8;
	}
}

.menu__item:nth-child(4) {
	margin-left: 29px;
}

.menu__item:nth-child(5) {
	padding-left: 29px;
}

.menu__link {
	font-weight: 400;
	font-size: 16px;
	line-height: 160%;
	text-align: right;
	color: #222528;
	text-decoration: none;
}

.menu__sublist {
	position: absolute;
	top: 64px;
	right: 20px;
	z-index: 3;
	display: block;
	margin: 0;
	padding: 0;
	list-style-type: none;
	background-color: white;
}

.menu__subitem {
	padding: 18px 22px 18px 31px;
	cursor: pointer;

	&:hover {
		background-color: #f2b236;
		box-shadow: 0 4px 4px 0 rgba(0, 0, 0, 0.25);
	}
}
</style>
