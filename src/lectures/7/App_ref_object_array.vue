<template>
	<div></div>
</template>

<script>
import { ref, reactive } from 'vue';
export default {
	setup() {
		//ref -> Object
		const count = ref(0);
		const state = reactive({
			count,
		});
		count.value++;
		count.value++;
		console.log('count.value: ', count.value); //ref 객체가 나옴
		//아래 로그는 undefined나옴
		// reactive()는 내부의 ref를 자동으로 언래핑해주기 때문에 value를 붙이면 안됨
		console.log('state.count.value: ', state.count.value);
		console.log('state.count: ', state.count); //0으로 잘 나옴

		// ref-> Array
		const message = ref('Hello');
		const arr = reactive([message]);
		console.log('arr[0]: ', arr[0].value);
		return {};
	},
};
</script>

<style lang="scss" scoped></style>
