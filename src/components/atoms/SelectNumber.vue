<template>
  <div>
    <label>
      <input
        type="number"
        :min="min"
        :max="max"
        :step="step"
        :name="name"
        :value="value"
      />
    </label>
    <p>{{ text }}</p>
  </div>
</template>

<script lang="ts" setup>
import { defineProps } from "vue";

defineProps({
  //数字の間隔
  step: {
    type: Number,
    default: 10,
  },
  //数字の最小
  min: {
    type: Number,
    default: 10,
  },
  //数字の最大
  max: {
    type: Number,
    default: 50,
  },
  //数字の規定値
  value: {
    type: Number,
    default: 10,
  },
  //inputのネーム属性
  name: {
    type: String,
    required: true,
  },
  //表示されるテキスト
  text: {
    type: String,
    required: true,
  },
});
</script>

<style lang="scss" scoped>
@import "./src/assets/scss/global";
div {
  font-size: $default;
  letter-spacing: 0.84px;
  color: $gray;
  font-weight: $regular;

  label {
    border-radius: 4px;
    border: $gray 1px solid;
    display: inline-block;
    position: relative;

    &::before,
    &::after {
      content: "";
      position: absolute;
      width: 0;
      height: 0;
      border-left: 5px solid transparent;
      border-right: 5px solid transparent;
      border-bottom: 5px solid $gray;
      right: 1rem;
    }
    &::before {
      top: 8px;
    }
    &::after {
      bottom: 8px;
      transform: rotate(180deg);
    }
    input[type="number"] {
      height: 3rem;
      padding: 0 1rem;

      &::-webkit-inner-spin-button,
      &::-webkit-outer-spin-button {
        opacity: 0;
        transform: translateX(2px) scale(1.2);
        position: relative;
        z-index: 40;
      }
    }
  }
  p {
    display: inline-block;
    margin-left: 1rem;
  }
}
</style>
