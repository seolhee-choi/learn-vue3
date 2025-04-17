<template>
	<div>
		<p>{{ message }}</p>
		<button v-on:click="addMessage">add Click</button>
	</div>
</template>

<script>
import { ref } from 'vue';

export default {
	setup() {
		let message = ref('Hello Vue!');

		const addMessage = () => {
			message.value = message.value + '!';
		};
		console.log('message: ', message);
		console.log('message.value: ', message.value);
		console.log('message typeof: ', typeof message.value);
		return {
			message,
			addMessage,
		};
	},
};
</script>

<style scoped></style>
