<template>
<TextLabel text="入社" type="green"/>
<Heading1 h1="これはタイトル1です"/>
</template>

<script lang="ts" setup>
import TextLabel from './components/atoms/TextLabel.vue';
import Heading1 from './components/atoms/Heading1.vue';
</script>

<style>
html {
  font-size: 10px;
  color: #484848;
  font-family: Noto Sans JP,Yu-Gothic;
}
* {
  margin: 0;
  font-size: unset;
  font-weight: unset;
}
</style>
