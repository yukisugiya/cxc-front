<template>
  <p :class='classObject'>{{ text }}</p>
</template>

<script lang="ts" setup>
import { computed, defineProps } from 'vue';

const props = defineProps({
  text: String,
  type: String,
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

<style scoped>
  p {
    font-size: 1.4rem;
    height: 3rem;
    display: flex;
    align-items: center;
    margin: 0 auto;
    padding: 0 1.2rem;
    letter-spacing: 0.84px;
    border-radius: 1.5rem;
    width: fit-content;
    box-sizing: border-box;
    font-weight: 400;
  }
  .c-label-lightgray{
    border: #D5D5D5 solid 1px;
    color: #9F9F9F;
  }
  .c-label-gray{
    border: #BDBDBD solid 1px;
    color: #808080;
  }
  .c-label-darkblue{
    background-color: #1755A6;
    border: #114993 solid 1px;
    color: #fff;
  }
  .c-label-blue{
    background-color: #5496D1;
    border: #4385C1 solid 1px;
    color: #fff;
  }
  .c-label-lightblue{
    background-color: #B7CEF5;
    border: #8AA3CC solid 1px;
    color: #13366C;
  }
  .c-label-darkpurple{
    background-color: #A39BFF;
    border: #948CF5 solid 1px;
    color: #FFF;
  }
  .c-label-purple{
    background-color: #E3D7FF;
    border: #DCD2EF solid 1px;
    color: #48288B;
  }
  .c-label-lightpurple{
    background-color: #F9F0FF;
    border: #F4E3FF solid 1px;
    color: #7C3296;
  }
  .c-label-lightpink{
    background-color: #FFE2F6;
    border: #FFDDE8 solid 1px;
    color: #811A3B;
  }
  .c-label-pink{
    background-color: #FFCBDC;
    border: #FFC1D4 solid 1px;
    color: #81334C;
  }
  .c-label-red{
    background-color: #DB675A;
    border: #CE5B4E solid 1px;
    color: #fff;
  }
  .c-label-darkorange{
    background-color: #FEC7AF;
    border: #FAB89C solid 1px;
    color: #8F4A2A;
  }
  .c-label-orange{
    background-color: #FFE1BA;
    border: #F2D8B5 solid 1px;
    color: #84571C;
  }
  .c-label-yellow{
    background-color: #FFE86C;
    border: #FAE368 solid 1px;
    color: #72640F;
  }
  .c-label-lightgreen{
    background-color: #D0EFCD;
    border: #B7DDB4 solid 1px;
    color: #246447;
  }
  .c-label-green{
    background-color: #45D592;
    border: #3ECB89 solid 1px;
    color: #026837;
  }
  .c-label-darkgreen{
    background-color: #1BA664;
    border: #229A64 solid 1px;
    color: #fff;
  }
</style>