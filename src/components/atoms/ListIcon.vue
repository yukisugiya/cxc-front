<template>
  <a>
    <i :class="iconName"></i>
    {{ text }}
    <i :class="arrowClass"  v-if="arrowShow"></i>
  </a>
</template>

<script lang="ts" setup>
import { defineProps, computed } from "vue";

const props = defineProps({
  //リストに表示するテキスト
  text: {
    type: String,
    required: true,
  },
  //リストに表示するアイコン
  icon: {
    type: String,
    required: true,
  },
  //矢印の表示
  arrow: {
    type: Boolean,
    default: false
  }
});
//矢印の表示処理
const arrowClass = computed(() => props.arrow == true ? 'arrow fas fa-chevron-right' : '' )
const arrowShow = computed(() => props.arrow != '' );

const iconName = computed(() => "icon far fa-" + props.icon );
</script>

<style lang="scss" scoped>
a {
  font-size: 1.4rem;
  color: #929292;
  transition: 0.2s;
  line-height: 4.2rem;
  position: relative;
  display: inline-block;
  width: 100%;
  box-sizing: border-box;
  padding-left: 4rem;
  border-radius: 0 2.1rem 2.1rem 0;
  cursor: pointer;
  font-weight: 400;
  letter-spacing: 0.84px;

  &:hover,
  &.active {
    color: #3b3c3c;
    background-color: #f8f8f8;
  }
  &.active i.arrow {
    transform: translateY(-50%) rotate(90deg);
  }
  i.icon {
    font-size: 1.6rem;
    margin-right: 1rem;
  }
  i.arrow {
    font-size: 6px;
    position: absolute;
    top: 55%;
    transform: translateY(-55%);
    right: 2rem;
    transition: 0.2s;
  }
}
</style>
