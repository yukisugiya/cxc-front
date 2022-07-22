<template>
  <a :href="url" @mouseover="mousemove" @mouseout="mousemove">
    <i :class="iconName"></i>
    <p v-if="isActive == true">{{ tipText }}</p>
  </a>
</template>

<script lang="ts" setup>
import { defineProps, ref, computed } from "vue";

const props = defineProps({
  //チップツールに表示するテキスト
  tipText: {
    type: String,
    required: true,
  },
  //アイコンのURL
  url: {
    type: String,
    required: true,
  },
  //アイコンの名前
  icon: {
    type: String,
    default: "user",
  },
});

const iconName = computed(() => "fas fa-" + props.icon);

const isActive = ref(false);

const mousemove = () => {
  isActive.value = !isActive.value;
};
</script>

<style lang="scss" scoped>
@import "./src/assets/scss/global";

a {
  font-size: $default;
  color: $gray;
  position: relative;
  width: 3rem;
  line-height: 3rem;
  display: inline-block;
  text-align: center;

  &:hover {
    color: $gray-4e;
  }
  p {
    color: $white;
    border-radius: 4px;
    background-color: $gray-4e;
    font-size: 1rem;
    font-weight: $medium;
    position: absolute;
    letter-spacing: 0.6px;
    padding: 0.7rem 1rem;
    bottom: -3rem;
    width: max-content;
    left: 50%;
    transform: translateX(-50%);
    line-height: 1;

    &::before {
      content: "";
      width: 0;
      height: 0;
      border-left: 4px solid transparent;
      border-right: 4px solid transparent;
      border-bottom: 6px solid $gray-4e;
      position: absolute;
      top: -6px;
      left: 50%;
      transform: translateX(-50%);
    }
  }
}
</style>
