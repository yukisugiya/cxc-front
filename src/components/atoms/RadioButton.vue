<template>
  <label>
    <input type="radio" name="name" :checked="checked"/>
    <span></span>
    {{ label }}
  </label>
</template>

<script lang="ts" setup>
import { defineProps } from "vue";

const props = defineProps({
  //ラベルに表示するテキスト
  label: {
    type: String,
    required: true,
  },
  name: {
    type: String,
    required: true,
  },
   checked: {
    type: Boolean,
  },
});
</script>

<style lang="scss" scoped>
@import "./src/assets/scss/global";
label {
  font-size: $large;
  letter-spacing: 0.94px;
  font-weight: $regular;
  position: relative;
  cursor: pointer;
  padding-left: 2rem;

  span {
    display: inline-block;
    border: $off-white solid 2px;
    width: 15px;
    height: 15px;
    border-radius: 50%;
    position: absolute;
    top: 60%;
    transform: translateY(-60%);
    left: 0;

    &::after {
      content: "";
      width: 11px;
      height: 11px;
      border-radius: 50%;
      background-color: $orange;
      position: absolute;
      opacity: 0;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
    }
  }
  input[type="radio"]:checked + span::after {
    opacity: 1;
  }
  input {
    opacity: 0;
    position: absolute;
  }
}
</style>
