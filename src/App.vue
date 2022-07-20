<template>
<Hamburger @toggleActive="aa" />
</template>

<script lang="ts" setup>
import Hamburger from './components/atoms/Hamburger.vue';
const aa = () => {
    console.log(9)
}
</script>
