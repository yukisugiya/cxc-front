<template>
<TextLabel text="入社" type="green"/>
<Heading2 h2="これはタイトル２です"/>
</template>

<script lang="ts" setup>
import TextLabel from './components/atoms/TextLabel.vue';
import Heading2 from './components/atoms/Heading2.vue';
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
