<template>
  <a :href="url" @click="toggleActive" :class="{ active: isActive }">
    <i :class="iconName"></i>
    <span>{{ text }}</span>
    <i :class="arrowClass" v-if="props.arrow"></i>
  </a>
</template>

<script lang="ts" setup>
import { defineProps, computed, defineEmits, ref } from "vue";

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
  //リンク紐付け
  url: {
    type: String,
  },
  //矢印の表示
  arrow: {
    type: Boolean,
    default: false,
  },
});

const emit = defineEmits(["list-click"]);

const isActive = ref(false);

const toggleActive = () => {
  emit("list-click");
  //クリックした時の処理
  isActive.value = !isActive.value;
};

//矢印の表示処理
const arrowClass = computed(() => props.arrow == true ? "fas fa-chevron-right arrow" : "" );

const iconName = computed(() => "icon far fa-" + props.icon);
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
