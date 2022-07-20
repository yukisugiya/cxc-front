<template>
  <button type="button" @click="$emit('Hamburger-event')">
    <i
      @click="toggleActive"
      class="fas fa-bars"
      :class="{ active: isActive }"
    ></i>
  </button>
</template>

<script lang="ts" setup>
import { ref } from "vue";

const isActive = ref(false);
const toggleActive = () => {
  isActive.value = !isActive.value;
};
</script>

<style lang="scss" scoped>
@import "./src/assets/scss/global";
button {
  i {
    font-size: 1.6rem;
    color: $base;
    transition: 0.3s;
    
    &.active {
      transform: rotate(180deg);
    }
  }
}
</style>
