<template>
  <h1>{{ headingText }}</h1>
</template>

<script lang="ts" setup>
import { defineProps } from 'vue';

const props = defineProps({
  headingText: { //表示するテキスト
		type: String, 
		required: true
	}
})
</script>

<style scoped lang="scss">
h1 {
  font-size: 2.9rem;
  color: #3B3C3C;
  letter-spacing: 1.74px;
  font-weight: 500;
}
</style>