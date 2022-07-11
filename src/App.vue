<template>
<TextLabel text="入社" type="green"/>
<SelectBox :options="[{name: 'n'},{name: 'kk'}]"/>
</template>

<script lang="ts" setup>
import TextLabel from './components/atoms/TextLabel.vue';
import SelectBox from './components/atoms/SelectBox.vue';
</script>
