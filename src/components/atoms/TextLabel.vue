<template>
  <p>{{ text }}</p>
</template>

<script lang="ts">
import { defineComponent } from 'vue';

export default defineComponent({
  name: 'TextLabel',
  props:{
    text: String
  }
});
</script>

<style scoped>
  p {
    font-size: 1.4rem;
    height: 3rem;
    display: flex;
    align-items: center;
    margin: 0 auto;
    padding: 0 1.2rem;
    letter-spacing: 0.08em;
    border-radius: 1.5rem;
    width: fit-content;
    box-sizing: border-box;
  }
  .label-green{
    background-color: #1BA664;
    border: #229A64 solid 1px;
    color: #fff;
  }
  .label-blue{
    background-color: #1755A6;
    border: #114993 solid 1px;
    color: #fff;
  }
  .label-red{
    background-color: #DB675A;
    border: #CE5B4E solid 1px;
    color: #fff;
  }
  .label-purple{
    background-color: #E3D7FF;
    border: #DCD2EF solid 1px;
    color: #48288B;
  }
  .label-orange{
    background-color: #FFE1BA;
    border: #F2D8B5 solid 1px;
    color: #84571C;
  }
</style>