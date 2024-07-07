<script setup>

import Button from "@/components/UI components/Button.vue";
import InputFile from "@/components/UI components/InputFile.vue";
</script>

<template>
  <form class="bg-panel tricking-wide mb-5 md:mb-52">
<!--  title  panel-->
    <div class="px-5 md:px-12 pt-9 pb-6 grid lg:grid-cols-7 w-full gap-5 items-center">
      <div>
        <label for="title" class="text-theme text-xl lg:float-right">Введите заголовок:</label>
      </div>
      <div class="lg:col-span-6">
        <input type="text" name="title" class="w-full lg:w-1/2">
      </div>
    </div>
<!--    about panel-->
    <div class="px-5 md:px-12 pt-9 pb-6 grid lg:grid-cols-7 w-full gap-5 border_custom">
      <div>
        <label for="about" class="text-theme text-xl lg:float-right">Описание:</label>
      </div>
      <div class="lg:col-span-6 lg:pr-36">
        <textarea name="about" id="" cols="30" rows="10" class="w-full"></textarea>
      </div>
    </div>

<!--buttons panel-->
    <div class="px-5 md:px-12 pb-6 grid lg:grid-cols-7 w-full gap-5">
      <div>

      </div>
      <div class="col-span-6 flex flex-col md:flex-row gap-5">
        <Button text="Опубликовать" class="text-lg md:text-xl"/>

        <InputFile text="Прикрепить файл" class="w-full md:w-56 h-12"/>
      </div>
    </div>


  </form>

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

  button{
    padding: 6px 20px;
  }

</style>