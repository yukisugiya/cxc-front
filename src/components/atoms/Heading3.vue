<template>
  <h3>{{ h3 }}</h3>
</template>

<script lang="ts" setup>
import { defineProps } from 'vue';

const props = defineProps({
  h3: String,
})
</script>

<style scoped>
h3 {
  font-size: 1.6rem;
  font-weight: 500;
  letter-spacing:0.96px;
  color: #6E6E6E;
}
</style>