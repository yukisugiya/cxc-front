<template>
  <button :class="className" :type="type" @click="$emit('event')">
  <i :class="iconName" v-if="iconShow"></i>{{ text }}
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
  },
  disabled: {
    type: Boolean,
    default: false
  }
});

const className = computed(() => ({
  "c-button-default": props.color == "default",
  "c-button-cta": props.color == "cta",
  "c-button-primary": props.color == "primary",
  "disabled": props.disabled == "true",
}));
//iconの値が空だった場合の処理
const iconShow = computed(() => props.icon != '' );

const iconName = computed(() => "fas fa-" + props.icon );
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
  padding: 0 1rem;
  
  i {
    margin-right: 0.4rem;
  }
  &.disabled {
    pointer-events: none;
  }
  &.c-button {
    &-default {
      color: $gray;
      background-color: $ghost-white;
      border: $silver 1px solid;
      font-size: $default;

      &:hover,
      &:active {
        background-color: $ea-white;
      }
      &.disabled{
        color: $sky-gray;
        background-color: $f4-white;
        border-color: $de-white;
      }
    }
    &-cta {
      color: $white;
      background-color: $yellow-orange;

      &:hover,
      &:active {
        background-color: $yellow-red;
      }
      &.disabled{
        background-color: $pale-orange;
      }
    }
    &-primary {
      color: $marigold;
      background-color: $white;
      border: solid 1px $marigold;

      &:hover,
      &:active {
        background-color: $f7-white;
        color: $mandarin-orange;
        border-color: $mandarin-orange;
      }
      &.disabled{
        background-color: $ghost-white;
        color: $flesh;
        border-color: $flesh;
      }
    }
  }
}
</style>
