<template>
  <p :class="classObject">{{ text }}</p>
</template>

<script lang="ts" setup>
import { computed, defineProps } from 'vue';

const props = defineProps({
  text: { //表示するテキスト
    type: String,
    required: true
  },
  type: { //ラベルの色
    type: String,
    default: 'lightgray'
  }
})

const classObject = computed(() => ({
  'c-label-lightgray': props.type == 'lightgray',
  'c-label-gray': props.type == 'gray',
  'c-label-darkblue': props.type == 'darkblue',
  'c-label-blue': props.type == 'blue',
  'c-label-lightblue': props.type == 'lightblue',
  'c-label-darkpurple': props.type == 'darkpurple',
  'c-label-purple': props.type == 'purple',
  'c-label-lightpurple': props.type == 'lightpurple',
  'c-label-lightpink': props.type == 'lightpink',
  'c-label-pink': props.type == 'pink',
  'c-label-red': props.type == 'red',
  'c-label-darkorange': props.type == 'darkorange',
  'c-label-orange': props.type == 'orange',
  'c-label-yellow': props.type == 'yellow',
  'c-label-lightgreen': props.type == 'lightgreen',
  'c-label-green': props.type == 'green',
  'c-label-darkgreen': props.type == 'darkgreen',
}))
</script>

<style lang="scss" scoped>
  p {
    font-size: 1.4rem;
    height: 3rem;
    display: flex;
    align-items: center;
    padding: 0 1.2rem;
    letter-spacing: 0.84px;
    border-radius: 1.5rem;
    width: fit-content;
    font-weight: 400;
  }
  .c-label {
    &-lightgray {
      border: #D5D5D5 solid 1px;
      color: #9F9F9F;
    }
    &-gray {
      border: #BDBDBD solid 1px;
      color: #808080;
    }
    &-darkblue {
      background-color: #1755A6;
      border: #114993 solid 1px;
      color: #fff;
    }
    &-blue {
      background-color: #5496D1;
      border: #4385C1 solid 1px;
      color: #fff;
    }
    &-lightblue {
      background-color: #B7CEF5;
      border: #8AA3CC solid 1px;
      color: #13366C;
    }
    &-darkpurple {
      background-color: #A39BFF;
      border: #948CF5 solid 1px;
      color: #FFF;
    }
    &-purple {
      background-color: #E3D7FF;
      border: #DCD2EF solid 1px;
      color: #48288B;
    }
    &-lightpurple{
      background-color: #F9F0FF;
      border: #F4E3FF solid 1px;
      color: #7C3296;
    }
    &-lightpink {
      background-color: #FFE2F6;
      border: #FFDDE8 solid 1px;
      color: #811A3B;
    }
    &-pink {
      background-color: #FFCBDC;
      border: #FFC1D4 solid 1px;
      color: #81334C;
    }
    &-red {
      background-color: #DB675A;
      border: #CE5B4E solid 1px;
      color: #fff;
    }
    &-darkorange {
      background-color: #FEC7AF;
      border: #FAB89C solid 1px;
      color: #8F4A2A;
    }
    &-orange {
      background-color: #FFE1BA;
      border: #F2D8B5 solid 1px;
      color: #84571C;
    }
    &-yellow {
      background-color: #FFE86C;
      border: #FAE368 solid 1px;
      color: #72640F;
    }
    &-lightgreen {
      background-color: #D0EFCD;
      border: #B7DDB4 solid 1px;
      color: #246447;
    }
    &-green {
      background-color: #45D592;
      border: #3ECB89 solid 1px;
      color: #026837;
    }
    &-darkgreen {
      background-color: #1BA664;
      border: #229A64 solid 1px;
      color: #fff;
    }
  }
</style>