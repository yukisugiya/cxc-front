<template>
  <p>{{ text }}</p>
</template>

<script lang="ts" setup>
import { defineProps } from "vue";

defineProps({
  //表示するテキスト
  text: {
    type: String,
    required: true,
  }
});
</script>

<style lang="scss" scoped>
@import "./src/assets/scss/global";
p {
  font-size: 1.3rem;
  font-weight: $regular;
  letter-spacing: 0.78px;
  color: $gray-92;
  position: relative;
  padding-left: 1rem;
  transition: 0.2s;
  display: inline-block;
  cursor: pointer;

  &::before {
    content: "";
    height: 6px;
    width: 6px;
    border-radius: 50%;
    background-color: $gray-92;
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    left: 0;
  }
  &:hover,
  &.active {
    color: $navy;

    &::before {
      background-color: $navy;
    }
  }
}
</style>
