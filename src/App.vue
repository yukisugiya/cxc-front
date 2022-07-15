<template>
<ButtonBasic text="削除" color="cta" type="submit" icon="times" disabled="false" @event="aaaa"/>
</template>

<script lang="ts" setup>
import ButtonBasic from './components/atoms/ButtonBasic.vue';

const aaaa = () => {alert('hello')}
</script>
