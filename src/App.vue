<script setup>
import {RouterLink, RouterView, useRoute} from 'vue-router'
import {onMounted, ref, computed} from "vue";
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
import Aside from "@/components/Aside.vue";
import MainView from "@/views/MainView.vue";
import BreadCrumb from "@/components/BreadCrumb.vue";


const auth = ref(true);

const route = useRoute();
const path = computed(() => route.path);

</script>

<template>
  <div class="header_container">
    <div class="container">
      <Header :auth="auth" />
    </div>
  </div>
  <div class="container">
    <BreadCrumb :path="path" v-if="path !== '/'" />

    <div class="grid grid-cols-6 pt-5 gap-5">
      <Aside :auth="auth" />

      <main class="col-span-5">
        <MainView />
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
