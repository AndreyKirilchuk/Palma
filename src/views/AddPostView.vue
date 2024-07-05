<script setup>

import Button from "@/components/UI components/Button.vue";
</script>

<template>
  <div class="bg-panel tricking-wide">
<!--  title  panel-->
    <div class="pl-12 pt-9 pb-6 grid grid-cols-7 w-full gap-5 items-center">
      <div>
        <label for="title" class="text-theme text-xl float-right">Введите заголовок:</label>
      </div>
      <div class="col-span-6">
        <input type="text" name="title">
      </div>
    </div>
<!--    about panel-->
    <div class="pl-12 pt-9 pb-6 grid grid-cols-7 w-full gap-5 border_custom">
      <div>
        <label for="title" class="text-theme text-xl float-right">Описание:</label>
      </div>
      <div class="col-span-6 pr-36">
        <textarea name="" id="" cols="30" rows="10" class="w-full"></textarea>
      </div>
    </div>

<!--buttons panel-->
    <div class="pl-12 pb-6 grid grid-cols-7 w-full gap-5">
      <div>

      </div>
      <div class="col-span-6 flex gap-5">
        <Button text="Опубликовать" class="text-xl"/>

        <div class="relative">
          <input type="file" name="fileInput" id="fileInput" hidden/>
          <label for="fileInput" class="custom-file-upload__button">
            Прикрепите файл
          </label>
        </div>

      </div>
    </div>


  </div>

</template>

<style scoped>
  .bg-panel{
    background:var(--var--bgpanelcolor);
    border-radius: 3px;
  }

  input, textarea {
    border: 1px solid var(--var--textcolor);
    border-radius: 3px;
    padding:6px 12px;
    color: var(--var--textcolor);
    background:var(--var--bodycolor);
    outline: none;
    font-size:16px;
  }

  .border_custom{
    border-top: 1px solid var(--var--linecolor);
  }

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

  button{
    padding: 6px 20px;
  }

</style>