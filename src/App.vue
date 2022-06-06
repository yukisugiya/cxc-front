<template>
  <div id="nav">
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
  </div>
    <TextLabel text="入社" class="label-green" />
    <TextLabel text="面接待ち" class="label-purple" />
    <TextLabel text="入社" class="label-blue" />
    <TextLabel text="面接待ち" class="label-red" />
    <TextLabel text="面接待ち" class="label-orange" />
  <router-view/>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import TextLabel from './components/atoms/TextLabel.vue';

export default defineComponent({
  components: {
    TextLabel
  },
});
</script>

<style>
html {
  font-size: 10px;
  font-family: Noto Sans JP,Yu-Gothic;
}
* {
  margin: 0;
}
#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
