<template>
  <p :class="classObject">{{ text }}</p>
</template>

<script lang="ts" setup>
import { computed, defineProps } from "vue";

const props = defineProps({
  text: {
    //表示するテキスト
    type: String,
    required: true,
  },
  type: {
    //ラベルの色
    type: String,
    default: "lightgray",
  },
});

const classObject = computed(() => ({
  "c-label-lightgray": props.type == "lightgray",
  "c-label-gray": props.type == "gray",
  "c-label-darkblue": props.type == "darkblue",
  "c-label-blue": props.type == "blue",
  "c-label-lightblue": props.type == "lightblue",
  "c-label-darkpurple": props.type == "darkpurple",
  "c-label-purple": props.type == "purple",
  "c-label-lightpurple": props.type == "lightpurple",
  "c-label-lightpink": props.type == "lightpink",
  "c-label-pink": props.type == "pink",
  "c-label-red": props.type == "red",
  "c-label-darkorange": props.type == "darkorange",
  "c-label-orange": props.type == "orange",
  "c-label-yellow": props.type == "yellow",
  "c-label-lightgreen": props.type == "lightgreen",
  "c-label-green": props.type == "green",
  "c-label-darkgreen": props.type == "darkgreen",
}));
</script>

<style lang="scss" scoped>
@import "./src/assets/scss/global";
p {
  font-size: $medium;
  height: 3rem;
  display: flex;
  align-items: center;
  padding: 0 1.2rem;
  letter-spacing: 0.84px;
  border-radius: 1.5rem;
  width: fit-content;
  font-weight: $regular;
}
.c-label {
  &-lightgray {
    border: #d5d5d5 solid 1px;
    color: #9f9f9f;
  }
  &-gray {
    border: #bdbdbd solid 1px;
    color: #808080;
  }
  &-darkblue {
    background-color: #1755a6;
    border: #114993 solid 1px;
    color: #fff;
  }
  &-blue {
    background-color: #5496d1;
    border: #4385c1 solid 1px;
    color: #fff;
  }
  &-lightblue {
    background-color: #b7cef5;
    border: #8aa3cc solid 1px;
    color: #13366c;
  }
  &-darkpurple {
    background-color: #a39bff;
    border: #948cf5 solid 1px;
    color: #fff;
  }
  &-purple {
    background-color: #e3d7ff;
    border: #dcd2ef solid 1px;
    color: #48288b;
  }
  &-lightpurple {
    background-color: #f9f0ff;
    border: #f4e3ff solid 1px;
    color: #7c3296;
  }
  &-lightpink {
    background-color: #ffe2f6;
    border: #ffdde8 solid 1px;
    color: #811a3b;
  }
  &-pink {
    background-color: #ffcbdc;
    border: #ffc1d4 solid 1px;
    color: #81334c;
  }
  &-red {
    background-color: #db675a;
    border: #ce5b4e solid 1px;
    color: #fff;
  }
  &-darkorange {
    background-color: #fec7af;
    border: #fab89c solid 1px;
    color: #8f4a2a;
  }
  &-orange {
    background-color: #ffe1ba;
    border: #f2d8b5 solid 1px;
    color: #84571c;
  }
  &-yellow {
    background-color: #ffe86c;
    border: #fae368 solid 1px;
    color: #72640f;
  }
  &-lightgreen {
    background-color: #d0efcd;
    border: #b7ddb4 solid 1px;
    color: #246447;
  }
  &-green {
    background-color: #45d592;
    border: #3ecb89 solid 1px;
    color: #026837;
  }
  &-darkgreen {
    background-color: #1ba664;
    border: #229a64 solid 1px;
    color: #fff;
  }
}
</style>