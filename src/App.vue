<template>
<TextLabel text="入社" type="green"/>
<SelectBox :options="[
        {name: 'kkkllllllllllllllllllllllllllllk', value: '@gmail.com', hidden: true},
        {name: 'yahoo.co.jp', value: '@yahoo.co.jp'}
    ]"/>
</template>

<script lang="ts" setup>
import TextLabel from './components/atoms/TextLabel.vue';
import SelectBox from './components/atoms/SelectBox.vue';
</script>
