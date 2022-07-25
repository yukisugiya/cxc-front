<template>
  <p>
    <span v-if="square == true">■</span>
    {{ text }}
    <span v-if="required == true" class="required">*</span>
  </p>
</template>

<script lang="ts" setup>
import { defineProps } from "vue";

defineProps({
  //表示するテキスト
  text: {
    type: String,
    required: true,
  },
  //四角の表示
  square: {
    type: Boolean,
    default: false
  },
  //アスタリスクの表示
  required: {
    type: Boolean,
    default: false
  }
});
</script>

<style scoped lang="scss">
@import "./src/assets/scss/global";

p{
  letter-spacing: $wide-spacing;
  font-size: $large;
  color: $navy;
  font-weight: $medium;

  & .required{
    color: $orange;
  }
}
</style>
