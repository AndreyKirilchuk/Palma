<script setup>
import {RouterView, useRoute} from 'vue-router'
import {ref, computed, watch, provide, onMounted} from "vue";
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
import Aside from "@/components/Aside.vue";
import BreadCrumb from "@/components/BreadCrumb.vue";
import SearchCrumb from "@/components/SearchCrumb.vue";
import Burger from "@/components/Burger.vue";
import Button from "@/components/UI components/Button.vue";


const auth = ref(true);

const route = useRoute();
const path = computed(() => route.path);
const burgerActive = ref(false);

const showFullMain = computed(() => {
  return path.value === '/addpost' || path.value === '/profile/settings';
});

const body = ref(document.body);

watch(path, (newPath) => {
  if (
      newPath === '/login' ||
      newPath === '/signup' ||
      newPath === '/renamepass' ||
      newPath === '/recover'
  ) {
    body.value.classList.add('active');
  } else {
    body.value.classList.remove('active');
  }
});

  // toggleTheme
  const toggleTheme = (event) => {
    localStorage.setItem('theme', event.target.value);
    setTheme()
  }

  const setTheme = () => {
    document.body.removeAttribute('light');
    document.body.removeAttribute('dark');
    document.body.removeAttribute('violet');
    document.body.setAttribute(localStorage.getItem('theme'), '');
  }

  onMounted(() => {
    setTheme()
  });

  const openBurger = () => {
    burgerActive.value = true
    body.value.classList.add('active')
  }

  const closeBurger = () => {
    burgerActive.value = false
    body.value.classList.remove('active')
  }

  const toggleAuth = () => {
    auth.value = !auth.value
  }


  provide('toggleTheme', toggleTheme);
  provide('burger', {
    openBurger,
    closeBurger
  });


</script>

<template>
  <Burger :burgerActive="burgerActive" :auth="auth" />
  <div class="header_container">
    <div class="container">
      <Header :auth="auth" />
    </div>
  </div>

  <div class="container">
    <BreadCrumb :path="path" v-if="path !== '/' && path !== '/search'" />
    <SearchCrumb v-if="path === '/search'"/>
    <div class="grid grid-cols-4 md-grid-cols-5 lg:grid-cols-6 pt-5 gap-3 xl:gap-5">
      <Aside :auth="auth" v-if="path !== '/addpost' && path !== '/profile/settings'" class="hidden md:block"/>

      <main :class="{'active': showFullMain}">
        <RouterView />
      </main>
    </div>
  </div>

  <div class="footer_container mt-7">
    <div class="container">
      <Footer :auth="auth" />
      <Button @click="toggleAuth" text="Сменить" class="w-full"/>
    </div>
  </div>

</template>

<style scoped>
  .header_container{
    padding: 15px 0px;
    border-bottom: 1px solid var(--var--linecolor);
  }


  .footer_container {
    padding: 15px 0px;
    border-top: 1px solid var(--var--linecolor);
  }

  main{
    grid-column: span 4;
  }

  @media (min-width: 768px) {
    main{
      grid-column: span 3;
    }

    main.active{
      grid-column: span 4;
    }

    .header_container, footer_container{
      padding: 25px 0px;
    }
  }
  
  @media (min-width: 1024px) {
    main{
      grid-column: span 5;
    }
    main.active{
      grid-column: span 6;
    }
  }
</style>
