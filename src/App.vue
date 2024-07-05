<script setup>
import {RouterLink, RouterView, useRoute} from 'vue-router'
import { ref, computed } from "vue";
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
import Aside from "@/components/Aside.vue";
import BreadCrumb from "@/components/BreadCrumb.vue";
import SearchCrumb from "@/components/SearchCrumb.vue";


const auth = ref(true);

const route = useRoute();
const path = computed(() => route.path);

const bodyRef = ref(null);

const showFullMain = computed(() => {
  return path.value === '/addpost' || path.value === '/profile/settings';
});

</script>

<template>
  <div class="header_container">
    <div class="container">
      <Header :auth="auth" />
    </div>
  </div>
  <div class="container">
    <BreadCrumb :path="path" v-if="path !== '/' && path !== '/search'" />
    <SearchCrumb v-if="path === '/search'"/>
    <div class="grid grid-cols-6 pt-5 gap-5">
      <Aside :auth="auth" v-if="path !== '/addpost' && path !== '/profile/settings'"/>

      <main :class="{ 'col-span-6': showFullMain, 'col-span-5': !showFullMain }" >
        <RouterView />
      </main>
    </div>
  </div>

  <div class="footer_container mt-7">
    <div class="container">
      <Footer :auth="auth" />
    </div>
  </div>

</template>

<style scoped>
  .header_container{
    padding: 25px 0px;
    border-bottom: 1px solid var(--var--linecolor);
  }

  .footer_container {
    padding: 25px 0px;
    border-top: 1px solid var(--var--linecolor);
  }
</style>
