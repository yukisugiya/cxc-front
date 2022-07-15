<template>
  <h1>{{ headingText }}</h1>
</template>

<script lang="ts" setup>
import { defineProps } from 'vue';

defineProps({
  headingText: { //表示するテキスト
		type: String, 
		required: true
	}
})
</script>

<style scoped lang="scss">
@import "./src/assets/scss/global";
h1 {
  font-size: 2.9rem;
  color: $navy;
  letter-spacing: 1.74px;
  font-weight: $medium;
}
</style>