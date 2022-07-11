<template>
  <h2>{{ headingText }}</h2>
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

<style lang="scss" scoped>
@import "./src/assets/scss/global";
h2 {
  font-size: $x-large;
  font-weight: $medium;
  letter-spacing: 1.2px;
  color: $dark-gray;
}
</style>