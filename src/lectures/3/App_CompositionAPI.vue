<template>
	<div>
		<button v-on:click="increment">Counter: {{ counter }}</button>
	</div>
</template>

<script>
import { ref, onMounted } from 'vue';

export default {
	setup() {
		const counter = ref(0);

		const increment = () => {
			counter.value++;
		};

		onMounted(() => {
			console.log('컴포넌트 마운트됨');
		});

		return {
			counter,
			increment,
		};
	},
};
</script>

<style></style>
