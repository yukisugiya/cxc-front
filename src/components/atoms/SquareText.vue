<template>
  <p>
    <span v-if="(square == true)">■</span>
    {{ text }}
    <span v-if="(required == true)" class="required">*</span>
  </p>
</template>

<script lang="ts" setup>
import { defineProps } from "vue";

defineProps({
  text: {
    type: String,
    required: true,
  },
  square: {
    type: Boolean,
    default: true
  },
  required: {
    type: Boolean,
    default: true
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
