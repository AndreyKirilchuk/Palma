<script setup>
  defineProps({
    text: String,
  })
</script>

<template>
  <div class="relative">
    <input type="file" name="fileInput" id="fileInput" hidden/>
    <label for="fileInput" class="custom-file-upload__button">
      {{ text }}
    </label>
  </div>

</template>

<style scoped>
  .custom-file-upload__button{
    position: absolute;
    left: 0;
    background: var(--var--filecolor);
    width: 100% ;
    height: 100%;
    text-align: center;
    color: white;
    font-weight: 500;
    align-content: center;
    border-radius: 3px;
    font-size: 16px;
    cursor: pointer;
    transition: 0.3s;
  }

  @media (min-width: 640px) {
    .custom-file-upload__button{
      font-size: 20px;
    }
  }
</style>