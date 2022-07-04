<template>
  <p>{{ text }}</p>
</template>

<script lang="ts" setup>
import { defineProps } from "vue";

const props = defineProps({
  //表示するテキスト
  text: {
    type: String,
    required: true,
  },
});
</script>

<style lang="scss" scoped>
p {
  font-size: 1.3rem;
  font-weight: 400;
  letter-spacing: 0.78px;
  color: #929292;
  position: relative;
  padding-left: 1rem;
  transition: 0.2s;
  cursor: pointer;

  &::before {
    content: "";
    height: 6px;
    width: 6px;
    border-radius: 50%;
    background-color: #929292;
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    left: 0;
  }
  &:hover,
  &.active {
    color: #3b3c3c;

    &::before {
      background-color: #3b3c3c;
    }
  }
}
</style>
