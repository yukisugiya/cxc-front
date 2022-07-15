<template>
  <button type="button" @click='toggleActive' :class="{'active': isActive}">
    <i class="fas fa-bars"></i>
  </button>
</template>

<script lang="ts" setup>
import { ref } from "vue";

const isActive = ref(false);
const toggleActive = () =>{
  isActive.value = !isActive.value ;
}
</script>

<style lang="scss" scoped>
@import "./src/assets/scss/global";
button {
  transition: 0.3s;

  i {
    font-size: 1.6rem;
    color: $base;
  }
  &.active{
    transform: rotate(180deg);
  }
}
</style>
