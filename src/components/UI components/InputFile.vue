<script setup>

</script>

<template>
  <div class="relative">
    <input type="file" name="fileInput" id="fileInput" hidden/>
    <label for="fileInput" class="custom-file-upload__button">
      Прикрепите файл
    </label>
  </div>

</template>

<style scoped>
  .custom-file-upload__button{
    position: absolute;
    left: 0;
    background: var(--var--bgtogglebuttoncolor);
    width: 225px;
    height: 100%;
    text-align: center;
    color: var(--var--textcolor);
    font-weight: 500;
    align-content: center;
    border-radius: 3px;
    font-size: 20px;
    cursor: pointer;
    transition: 0.3s;
  }
</style>