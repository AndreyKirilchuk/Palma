<script setup>

import Button from "@/components/UI components/Button.vue";
import InputFile from "@/components/UI components/InputFile.vue";
import {inject} from "vue";

defineProps({
  modalEmail: Boolean,
  modalName:Boolean,
  modalAvatar:Boolean,
  modalObloshka:Boolean,
})

const closeModal = inject("closeModal")
</script>

<template>
  <div class="modal" @click="closeModal" />

  <form class="modal_inner">
    <div class="mb-5 flex justify-between items-center">
      <div class="modal_title">
        Изменить
        <span v-if="modalName">имя</span>
        <span v-if="modalEmail">адрес электронной почты</span>
        <span v-if="modalAvatar">аватар</span>
        <span v-if="modalObloshka">обложку профиля</span>
      </div>

      <svg width="18" height="18" viewBox="0 0 30 30" fill="none" xmlns="http://www.w3.org/2000/svg" @click="closeModal">
        <path fill-rule="evenodd" clip-rule="evenodd" d="M2.56066 0.43934C1.97487 -0.146447 1.02513 -0.146447 0.43934 0.43934C-0.146447 1.02513 -0.146447 1.97487 0.43934 2.56066L12.8787 15L0.439341 27.4393C-0.146446 28.0251 -0.146446 28.9749 0.439341 29.5607C1.02513 30.1464 1.97487 30.1464 2.56066 29.5607L15 17.1213L27.4393 29.5607C28.0251 30.1464 28.9749 30.1464 29.5607 29.5607C30.1464 28.9749 30.1464 28.0251 29.5607 27.4393L17.1213 15L29.5607 2.56066C30.1464 1.97487 30.1464 1.02513 29.5607 0.43934C28.9749 -0.146447 28.0251 -0.146447 27.4393 0.43934L15 12.8787L2.56066 0.43934Z" fill="white"/>
      </svg>

    </div>

    <div class="mb-7 text-xl h-10 flex gap-x-6 items-center text-theme" v-if="modalAvatar || modalObloshka" >
      Добавьте новый файл<InputFile class="h-12" text="Выбрать файл"  />
    </div>


    <div v-if="modalName" class="text-xl text-theme flex items-center gap-6 mb-7">
     <div class="w-48 text-right">Новое имя:</div> <input type="text" name="name" class="form_input w-full">
    </div>

    <div v-if="modalEmail" class="text-xl text-theme flex items-center gap-6 mb-7">
      <div class="w-48 text-right">Новый e-mail:</div> <input type="email" name="email" class="form_input w-full">
    </div>

    <div v-if="modalEmail" class="text-xl text-theme flex items-center gap-6 mb-7">
      <div class="w-48 text-right">Пароль:</div> <input type="password" name="password" class="form_input w-full">
    </div>

    <Button text="Сохранить изменения" @click="closeModal" v-if="modalAvatar || modalObloshka"/>

    <Button text="Изменить" @click="closeModal" class="float-right" v-if="modalName || modalEmail"/>
  </form>



</template>

<style scoped>
  .modal{
    position: fixed;
    left: 0;
    top: 0;
    background: var(--var--linecolor);
    width: 100%;
    height: 100%;
  }

  .modal_inner{
    position: fixed;
    top: 30%;
    left: 50%;
    transform: translate(-50%, -50%);
    max-width:800px;
    width: 800px;
    background: var(--var--modalcolor);
    box-shadow: 0px 0px 30px 1200px rgba(3,3,3,0.5);
    padding: 25px 30px;
    border-radius: 4px;
  }

  .modal_title{
    font-size: 24px;
    font-weight: 500;
    color:var(--var--textcolor)
  }

  svg{
    cursor:pointer;
  }
</style>