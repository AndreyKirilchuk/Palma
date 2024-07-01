<script setup>
  defineProps({
    text: String,
  })
</script>

<template>
  <button class="bg-primary py-2 px-7 rounded-sm text-xl">
    {{ text }}
  </button>
</template>

<style scoped>
  button{
    color: var(--var--btncolor);
    transition: 0.3s ease-in-out;
  }

  button:hover{
    background: rgba(255, 176, 58, 0.84);
  }
</style>