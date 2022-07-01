<template>
  <h2><i :class="iconName"></i>{{ headingText }}</h2>
</template>

<script lang="ts" setup>
import { defineProps, computed } from "vue";

const props = defineProps({
  headingText: { //表示するテキスト
    type: String,
    required: true,
  },
  icon: { //アイコンの種類
    type: String,
    default: 'search'
  }
});

const iconName = 'fas fa-' + props.icon;
</script>

<style scoped lang="scss">
h2 {
  font-size: 2rem;
  color: #6e6e6e;
  letter-spacing: 1.2px;
  font-weight: 500;

  i {
    position: relative;
    bottom: 1.5px;
    font-size: 1.4rem;
    margin-right: 0.5rem;
  }
}
</style>
