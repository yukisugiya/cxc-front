<template>
  <h1>{{ h1 }}</h1>
</template>

<script lang="ts" setup>
import { defineProps } from 'vue';

const props = defineProps({
  h1: String,
})
</script>

<style scoped>
h1 {
  font-size: 2.9rem;
  letter-spacing: 0.17em;
  font-weight: 500;
}
</style>