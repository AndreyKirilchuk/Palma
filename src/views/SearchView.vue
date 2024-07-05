<script setup>

import PostList from "@/components/PostList.vue";
</script>

<template>
  <div class="bg_panel text-theme text-2xl text-center py-5" v-if="1 === 2">
    По вашему запросу ничего не найдено
  </div>

  <PostList />
</template>

<style scoped>
  .bg_panel{
    background:var(--var--bgpanelcolor);
  }
</style>