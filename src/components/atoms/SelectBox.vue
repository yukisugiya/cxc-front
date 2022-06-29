<template>
  <label>
    <i class="fas fa-chevron-down"></i>
    <select>
      <option
        v-for="option in options"
        :key="option.name"
        :value="option.value"
        :hidden="option.hidden"
      >
        {{ option.name }}
      </option>
    </select>
  </label>
</template>

<script lang="ts" setup>
import { defineProps } from "vue";

const props = defineProps({
  //セレクトボックスのオプション
  options: {
    type: Array,
    required: true,
  },
});
</script>

<style lang="scss" scoped>
label {
  position: relative;
  display: inline-block;

  i {
    position: absolute;
    top: 50%;
    transform: translateY(-50%);
    font-size: 0.8rem;
    right: 2rem;
  }

  select {
    background-color: #f8f8f8;
    height: 3.6rem;
    border-radius: 4px;
    padding: 0 4rem 0 2rem;
    font-size: 1.4rem;
    letter-spacing: 0.84px;
    color: #6e6e6e;
    outline: none;
  }
}
</style>
