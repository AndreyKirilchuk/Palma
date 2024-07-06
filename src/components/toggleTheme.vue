<script setup>
import {inject, onMounted, ref} from 'vue';


  const toggleTheme = inject("toggleTheme");
  let thisTheme = ref('')

  onMounted( () => {
    thisTheme.value = localStorage.getItem("theme");
  });

</script>

<template>
    <select @change="toggleTheme">
      <option value="violet" :selected="thisTheme === 'violet' ? true : false">Фиолетовая</option>
      <option value="dark" :selected="thisTheme === 'dark' ? true : false">Темная</option>
      <option value="light" :selected="thisTheme === 'light' ? true : false">Светлая</option>
    </select>
</template>

<style scoped>
  select{
    background: #FFB03A;
    padding: 8px;
    border-radius: 3px;
    color: var(--var--btncolor);
    outline: none;
  }
</style>