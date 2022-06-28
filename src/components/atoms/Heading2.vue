<template>
  <h2>{{ headingText }}</h2>
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

<style lang="scss" scoped>
h2 {
  font-size: 2rem;
  font-weight: 500;
  letter-spacing: 1.2px;
  color: #484848;
}
</style>