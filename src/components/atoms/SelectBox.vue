<template>
  <label>
    <i class="fas fa-chevron-down"></i>
    <select>
      <option
        v-for="option in options"
        :key="option.name"
        :value="option.name"
        :hidden="option.hidden"
      >
        {{ option.name }}
      </option>
    </select>
  </label>
</template>

<script lang="ts" setup>
import { defineProps } from "vue";

defineProps({
  options: {
    type: Array,
    required: true,
    name: {
      type: String,
      required: true,
    },
    hidden: {
      type: Boolean,
    }
  }
});
</script>

<style lang="scss" scoped>
@import "./src/assets/scss/global";

label {
  position: relative;
  display: inline-block;
  background-color: $light-gray;

  i {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    font-size: 0.8rem;
    right: 2rem;
    z-index: 0;
  }
  select {
    height: 3.6rem;
    border-radius: 4px;
    padding: 0 4rem 0 2rem;
    font-size: $default;
    letter-spacing: 0.84px;
    color: $gray;
    position: relative;
    z-index: 10;
    background-color: none;
  }
}
</style>
