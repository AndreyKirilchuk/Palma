<script setup>

  import Aside from "@/components/Aside.vue";
  import {onMounted} from "vue";

  let thisTheme = '';
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

    <div class="">
      <select @change="toggleTheme">
        <option value="violet" :selected="thisTheme === 'violet' ? true : false">Фиолетовая</option>
        <option value="dark" :selected="thisTheme === 'dark' ? true : false">Темная</option>
        <option value="light" :selected="thisTheme === 'light' ? true : false">Светлая</option>
      </select>
    </div>
</template>
