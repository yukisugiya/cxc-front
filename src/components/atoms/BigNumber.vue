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
@import "./src/assets/scss/global";
p {
  font-size: $small;
  color: $gray;
  letter-spacing: 0.72px;
  font-weight: $regular;
}
em {
  font-size: 3rem;
  font-family: $mont;
  font-weight: $semi-bold;
  margin-right: 0.2rem;
  color: $off-white;
  &.active{
    color: $navy;
  }
}
</style>