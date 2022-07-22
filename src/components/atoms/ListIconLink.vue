<template>
  <a v-if="url" :href="url" :class="classObject">
    <i :class="iconName"></i>
    <span>{{ text }}</span>
  </a>
  <p v-else @click="toggleActive" :class="classObject">
    <i :class="iconName"></i>
    <span>{{ text }}</span>
    <i class="fas fa-chevron-right arrow"></i>
  </p>
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
    default: "file-alt",
  },
  //リンク紐付け
  url: {
    type: String,
  },
  mini: {
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

const classObject = computed(() => ({
  mini: props.mini == true,
  active: isActive.value == true,
}));

const iconName = computed(() => "icon far fa-" + props.icon);
</script>

<style lang="scss" scoped>
@import "./src/assets/scss/global";
a,
p {
  font-size: $default;
  color: $gray-92;
  transition: 0.2s;
  line-height: 4.2rem;
  position: relative;
  display: inline-block;
  max-width: 24rem;
  width: 100%;
  box-sizing: border-box;
  padding-left: 4rem;
  border-radius: 0 2.1rem 2.1rem 0;
  cursor: pointer;
  font-weight: $regular;
  letter-spacing: $default-spacing;
  background-color: $white;

  &:hover,
  &.active {
    color: $navy;
    background-color: $light-gray;
  }
  &.active i.arrow {
    transform: translateY(-50%) rotate(90deg);
  }
  i {
    &.icon {
      font-size: $large;
      margin-right: 1rem;
    }
    &.arrow {
      font-size: 6px;
      position: absolute;
      top: 55%;
      transform: translateY(-55%);
      right: 2rem;
      transition: 0.2s;
    }
  }
  &.mini {
    padding-left: 0;
    text-align: center;
    width: fit-content;
    display: block;
    border-radius: 0;
    width: 9rem;

    &::before {
      content: "";
      height: 100%;
      width: 3px;
      background-color: $navy;
      position: absolute;
      top: 0;
      left: 0;
      opacity: 0;
      transition: 0.2s;
    }
    &:hover,
    &.active {
      color: $navy;
      background-color: $white;

      &::before {
        opacity: 1;
      }
    }
    i {
      margin-right: 0;

      &.arrow {
        display: none;
      }
    }
    span {
      display: none;
    }
  }
}
</style>
