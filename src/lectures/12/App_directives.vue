<template>
	<div>
		<p>{{ msg }}</p>
		<p v-text="msg"></p>
		<p v-html="htmlStr"></p>
		<p v-text="htmlStr"></p>
		<p v-pre>{{ msg 안녕하세요 }}</p>
		<p v-once>{{ msg }}</p>
		<!-- v-once는 처음 한 번만 렌더링하고 이후엔 업데이트 안함-->
	</div>
</template>

<script>
import { ref } from 'vue';
export default {
	setup() {
		const msg = ref('안녕하세요');
		const htmlStr = ref('<strong>안녕!!!</strong>');

		return {
			msg,
			htmlStr,
		};
	},
};
</script>

<style lang="scss" scoped></style>
