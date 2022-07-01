<template>
  <p><em :class="className">{{ num }}</em>{{ text }}</p>
</template>

<script lang="ts" setup>
import { defineProps, computed } from 'vue';

const props = defineProps({
  //件数の数字
  num: {
    type: Number,
    required: true
  },
  text: {
    type: String,
    required: true
  }
})
//numが0以上の時に色が変わる処理
const className = computed(() => props.num > 0 ? 'active' : '')

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
  font-family: 'Montserrat', sans-serif;
  font-weight: 600;
  margin-right: 0.2rem;
  color: #E2E2E2;
  &.active{
    color: #3B3C3C;
  }
}
</style>