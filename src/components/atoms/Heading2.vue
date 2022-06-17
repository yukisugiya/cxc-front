<template>
  <h2>{{ h2 }}</h2>
</template>

<script lang="ts" setup>
import { defineProps } from 'vue';

const props = defineProps({
  h2: String,
})
</script>

<style scoped>
h2 {
  font-size: 2rem;
  letter-spacing: 1.2px;
  color: #484848;
}
</style>