<template>
  <p><em :class="classObject">{{ num }}</em>件</p>
</template>

<script lang="ts" setup>
import { defineProps, computed } from 'vue';

const props = defineProps({
  num: Number,//件数の数字
})

const classObject = computed(() => props.num > 0 ? 'active' : '')//numが0以上の時に色が変わる処理

</script>

<style lang="scss" scoped>
p {
  font-size: 1.2rem;
  color: #6E6E6E;
  letter-spacing: 0.72px;
  font-weight: 400;
}
em {
  font-size: 3rem;
  font-style: unset;
  font-family: 'Montserrat', sans-serif;
  font-weight: 600;
  margin-right: 0.2rem;
  color: #E2E2E2;
  &.active{
    color: #3B3C3C;
  }
}
</style>