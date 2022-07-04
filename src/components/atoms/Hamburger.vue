<template>
  <button type="button">
    <i class="fas fa-bars"></i>
  </button>
</template>

<script lang="ts" setup>
import { defineProps } from "vue";

const props = defineProps({});
</script>

<style lang="scss" scoped>
button {
  i {
    font-size: 1.6rem;
    color: #484848;
    transition: 0.2s;

    &:hover {
      opacity: 0.5;
    }
  }
}
</style>
