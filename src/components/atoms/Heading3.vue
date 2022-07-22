<template>
  <h3>{{ headingText }}</h3>
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

<style lang ="scss" scoped>
@import "./src/assets/scss/global";
h3 {
  font-size: $large;
  font-weight: $medium;
  letter-spacing: $wide-spacing;
  color: $gray;
}
</style>