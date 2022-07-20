<template>
  <a :href="url">
    <i :class="iconName"></i>
    <span>{{ text }}</span>
  </a>
</template>

<script lang="ts" setup>
import { defineProps, computed } from "vue";

const props = defineProps({
  text: {
    type: String,
    required: true,
  },
  icon: {
    type: String,
    default: "chevron-left",
  },
  url: {
    type: String,
    required: true,
  },
});

const iconName = computed(() => "fas fa-" + props.icon);
</script>

<style lang="scss" scoped>
@import "./src/assets/scss/global";

a {
  color: $gray;
  cursor: pointer;
  transition: 0.2s;
  display: inline-block;
  
  i {
    font-size: $x-small;
    margin-right: 0.5rem;
  }
  span {
    font-size: $default;
    font-weight: $medium;
    letter-spacing: 0.84px;
    border-bottom: $gray solid 1px;
    padding-bottom: 1px;
    display: inline-block;
  }
  &:hover {
    color: $base;
  }
}
</style>
