<script setup>
  defineProps({
    text: String,
  })
</script>

<template>
  <button class="bg-primary py-1.5 sm:py-2 px-4.5 2xl:px-7 text-lg sm:text-xl">
    {{ text }}
  </button>
</template>

<style scoped>
  button{
    color: var(--var--btncolor);
    transition: 0.3s ease-in-out;
    border-radius: 3px;
  }

  button:hover{
    background:rgba(255,176,58,0.85);
  }

</style>