<template>
  <button type="button">
    <i :class="iconName"></i><span>{{ text }}</span>
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
  cursor: pointer;
  transition: 0.2s;

  i {
    font-size: $x-small;
    margin-right: 0.5rem;
  }
  span{
    font-size: $default;
    font-weight: $medium;
    letter-spacing: 0.84px;
    border-bottom: $gray solid 1px;
    padding-bottom: 1px;
  }
  &:hover {
    color: $base;
  }
}
</style>
