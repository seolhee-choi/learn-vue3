<template>
	<div>
		<p>author: {{ author }}</p>
		<p>title: {{ title }}</p>
	</div>
</template>

<script>
import { reactive, toRef, toRefs } from 'vue';
export default {
	setup() {
		const book = reactive({
			author: 'Vue Team',
			year: '2023',
			title: 'Vue 3 Guide',
			description: '당신은 지금 바로 이 책을 읽습니다 ;)',
			price: '무료',
		});

		/* toRef : reactive 객체의 한 개 속성 / toRefs : reactive 객체의 모든 속성 */
		// const { author, title } = toRefs(book);
		const author = toRef(book, 'author');
		const title = toRef(book, 'title');

		return { book, author, title };
	},
};
</script>

<style lang="scss" scoped></style>
