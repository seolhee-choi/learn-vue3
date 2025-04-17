<template>
	<div></div>
</template>

<script>
import { reactive, readonly } from 'vue';

export default {
	setup() {
		const original = reactive({
			count: 0,
		});
		const copy = readonly(original);
		original.count++;
		copy.count++; // readonly로 감싸도 위에서 original.count++로 인해 count가 1이되어 copy값이 변경된 것 처럼 보임
		console.log('original count', original.count);
		console.log('copy count', copy.count);

		return {};
	},
};
</script>

<style lang="scss" scoped></style>
