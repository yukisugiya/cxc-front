<template>
  <button :class="className" :type="type">
  <i :class="iconName"></i>{{ text }}
  </button>
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
  },
  //ボタンのアイコン
  icon: {
    type: String,
  }
});

const className = computed(() => ({
  "c-button-default": props.color == "default",
  "c-button-cta": props.color == "cta",
  "c-button-primary": props.color == "primary",
}));

const iconName = 'fas fa-' + props.icon;
</script>

<style lang="scss" scoped>
@import "./src/assets/scss/global";
button {
  font-size: $large;
  letter-spacing: 0.96px;
  border-radius: 4px;
  line-height: 3.6rem;
  text-align: center;
  box-sizing: border-box;
  font-weight: $medium;
  transition: 0.2s;
  cursor: pointer;
  
  i {
    margin-right: 0.4rem;
  }
  &.c-button {
    &-default {
      color: $gray;
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
