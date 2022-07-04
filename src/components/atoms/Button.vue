<template>
  <button :class="className" :type="type">{{ text }}</button>
</template>

<script lang="ts" setup>
import { defineProps, computed } from "vue";

const props = defineProps({
  //ボタンに表示するするテキスト
  text: {
    type: String,
    required: true,
  },
  //ボタンのカラー
  color: {
    type: String,
    default: "default",
  },
  //ボタンのタイプ
  type: {
    type: String,
    default: "button",
  }
});

const className = computed(() => ({
  "c-button-default": props.color == "default",
  "c-button-cta": props.color == "cta",
  "c-button-primary": props.color == "primary",
}));
</script>

<style lang="scss" scoped>
button {
  font-size: 1.6rem;
  letter-spacing: 0.96px;
  border-radius: 4px;
  line-height: 3.6rem;
  min-width: 13rem;
  text-align: center;
  box-sizing: border-box;
  padding: 0 1.6rem;
  font-weight: 500;
  transition: 0.2s;
  cursor: pointer;

  &.c-button {
    &-default {
      color: #6e6e6e;
      background-color: #fcfcfc;
      border: #c7c7c7 1px solid;
      font-size: 1.4rem;

      &:hover,
      &:active {
        background-color: #eaeaea;
      }
      &.disabled{
        color: #B3B3B3;
        background-color: #F4F4F4;
        border-color: #DEDEDE;
      }
    }
    &-cta {
      color: #fff;
      background-color: #F87826;

      &:hover,
      &:active {
        background-color: #D8661E;
      }
      &.disabled{
        background-color: #EDBB9B;
      }
    }
    &-primary {
      color: #F08B4B;
      background-color: #fff;
      border: solid 1px #F08B4B;

      &:hover,
      &:active {
        background-color: #F7F7F7;
        color: #DB7B00;
        border-color: #DB7B00;
      }
      &.disabled{
        background-color: #FCFCFC;
        color: #F1CEA0;
        border-color: #F1CEA0;
      }
    }
  }
}
</style>
