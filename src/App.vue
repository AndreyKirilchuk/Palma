<script setup>
import { RouterLink, RouterView } from 'vue-router'
import {onMounted, ref} from "vue";
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'

let thisTheme = '';
const auth = ref(false);

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
  thisTheme = localStorage.getItem('theme');
});

</script>

<template>
  <div class="header_container">
    <div class="container">
      <Header :auth="auth" />
    </div>
  </div>
  <div class="container">
    <RouterView />
        <select @change="toggleTheme">
          <option value="violet" :selected="thisTheme === 'violet' ? true : false">Фиолетовая</option>
          <option value="dark" :selected="thisTheme === 'dark' ? true : false">Темная</option>
          <option value="light" :selected="thisTheme === 'light' ? true : false">Светлая</option>
        </select>
  </div>
  <div class="footer_container">
    <div class="container">
      <Footer :auth="auth" />
    </div>
  </div>

</template>

<style scoped>
  .header_container{
    padding: 25px 0px;
    border-bottom: 1px solid rgba(255,255,255,0.1);
  }

  .footer_container {
    padding: 25px 0px;
    border-top: 1px solid rgba(255,255,255,0.1);
  }
</style>
