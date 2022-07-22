<template>
  <button type="button" @click="toggleActive" :class="{ active: isActive }" >
    <i class="fas fa-bars"></i>
  </button>
</template>

<script lang="ts" setup>
import { ref, defineEmits } from "vue";

const emit = defineEmits(["Hamburger-event"]);

const isActive = ref(false);

const toggleActive = () => {
  emit("Hamburger-event");
  isActive.value = !isActive.value;
};
</script>

<style lang="scss" scoped>
@import "./src/assets/scss/global";
button {
  i {
    font-size: $large;
    color: $base;
    transition: 0.3s;
  }
  &.active i{
    transform: rotate(180deg);
  }
}
</style>
