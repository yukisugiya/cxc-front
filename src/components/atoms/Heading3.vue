<template>
  <h3>{{ headingText }}</h3>
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

<style lang ="scss" scoped>
h3 {
  font-size: 1.6rem;
  font-weight: 500;
  letter-spacing:0.96px;
  color: #6E6E6E;
}
</style>