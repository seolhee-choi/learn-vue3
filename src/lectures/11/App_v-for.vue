<template>
	<div>
		<ul>
			<template v-for="(item, index) in evenItmes" :key="item.id">
				<!-- <li v-if="item.id % 2 === 0"></li> -->
				<li>ID: {{ item.id }} / 인덱스: {{ index }} / {{ item.message }}</li>
			</template>
		</ul>
		<hr />
		<ul>
			<li v-for="(value, key, index) in myObject" :key="key">
				{{ index }} - {{ key }} - {{ value }}
			</li>
		</ul>
	</div>
</template>

<script>
import { computed, reactive } from 'vue';

export default {
	setup() {
		const items = reactive([
			{ id: 1, message: 'Java' },
			{ id: 2, message: 'HTML' },
			{ id: 3, message: 'CSS' },
			{ id: 4, message: 'JavaScript' },
		]);

		const evenItmes = computed(() => items.filter((item) => item.id % 2 === 0));
		const myObject = reactive({
			title: '제목',
			author: '홍길동',
			publishedAt: '2026-01-01',
		});

		return {
			items,
			evenItmes,
			myObject,
		};
	},
};
</script>

<style lang="scss" scoped></style>
