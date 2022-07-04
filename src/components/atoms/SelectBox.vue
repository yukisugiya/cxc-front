<template>
  <label for="aa">
    <i class="fas fa-chevron-down"></i>
    <select id="aa">
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
    name: {    
      type: String,
      required: true
    },
    value: {
    type: String,
    required: true
    },
    hidden: {
      type: Boolean,
    }
  }
});
</script>

<style lang="scss" scoped>
label {
  position: relative;
  display: inline-block;
  background-color: #f8f8f8;

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
    font-size: 1.4rem;
    letter-spacing: 0.84px;
    color: #6e6e6e;
    outline: none;
    position: relative;
    z-index: 10;
    background-color: none;
  }
}
</style>
