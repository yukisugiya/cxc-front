<template>
  <h2><i :class="iconName"></i>{{ headingText }}</h2>
</template>

<script lang="ts" setup>
import { defineProps, computed } from "vue";

const props = defineProps({
  headingText: {
    //表示するテキスト
    type: String,
    required: true,
  },
  icon: {
    //アイコンの種類
    type: String,
    default: "search",
  },
});
const iconName = computed(() => "fas fa-" + props.icon);
</script>

<style scoped lang="scss">
@import "./src/assets/scss/global";
h2 {
  font-size: $x-large;
  color: $gray;
  letter-spacing: 1.2px;
  font-weight: $medium;

  i {
    position: relative;
    bottom: 1.5px;
    font-size: $default;
    margin-right: 0.5rem;
  }
}
</style>