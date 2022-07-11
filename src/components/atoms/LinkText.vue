<template>
  <button type="button">
    <i :class="iconName"></i>
    {{ text }}
  </button>
</template>

<script lang="ts" setup>
import { defineProps } from "vue";

const props = defineProps({
  text: {
    type: String,
    required: true,
  },
  icon: {
    type: String,
    default: "chevron-left",
  },
});

const iconName = "fas fa-" + props.icon;
</script>

<style lang="scss" scoped>
@import "./src/assets/scss/global";
button {
  color: $gray;
  font-size: $default;
  font-weight: $medium;
  letter-spacing: 0.84px;
  border-bottom: $gray solid 1px;
  padding-bottom: 1px;
  position: relative;
  margin-left: 1.5rem;
  cursor: pointer;
  transition: 0.2s;

  i {
    position: absolute;
    font-size: 1.1rem;
    left: -1.5rem;
    top: 50%;
    transform: translateY(-50%);
  }
  &:hover {
    color: $base;
  }
}
</style>
