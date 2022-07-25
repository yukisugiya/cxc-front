<template>
<ListIconLink icon="file-alt" text="アンケート" @list-click="aaa" size="sm" />
<ListIconLink icon="file-alt" text="アンケート" @list-click="aaa"/>
<ListIconLink icon="comment-dots" text="匿名質問一覧" url="http://eishin-develop.sakura.ne.jp/cxc/index.html" />
</template>

<script lang="ts" setup>
import ListIconLink from './components/atoms/ListIconLink.vue';

const aaa = () => { console.log(9) }
</script>
<style>
html{
  background-color: #888;
}
</style>
