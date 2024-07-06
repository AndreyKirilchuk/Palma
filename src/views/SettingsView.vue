<script setup>
  import {ref, provide} from "vue";

  import Button from "@/components/UI components/Button.vue";
  import Modal from "@/components/Modal.vue";
  import ToggleTheme from "@/components/toggleTheme.vue";

  const body = ref(document.body);
  const modalActive = ref(false);
  const modalObloshka = ref(false);
  const modalAvatar = ref(false);
  const modalEmail = ref(false);
  const modalName = ref(false);

  const showModal = (el) => {
    if(el === "showObloshka"){
      modalObloshka.value = true;
    }else if(el === "showAvatar"){
      modalAvatar.value = true;
    }else if(el === "showEmail"){
      modalEmail.value = true;
    }else if(el === "showName"){
      modalName.value = true;
    }

    modalActive.value = true;
    body.value.classList.add('active')
  };

  const closeModal = () => {
    modalActive.value = false;
    body.value.classList.remove('active')
    modalObloshka.value = false;
    modalAvatar.value = false;
    modalEmail.value = false;
    modalName.value = false;
  }


  provide('closeModal', closeModal)

</script>

<template>
  <div class="bg-panel flex flex-col">
    <!--    theme-->
    <div class="input_container items-center">
      <div>
        Выберите тему:
      </div>
      <div class="flex gap-5 items-center">
        <ToggleTheme/>
      </div>
    </div>
<!--    name-->
    <div class="input_container items-center">
      <div>
        Ваше имя:
      </div>
      <div class="flex gap-5 items-center">
        Иван иванов

        <Button text="Изменить" @click="showModal('showName')"/>
      </div>
    </div>
<!--    email-->
    <div class="input_container items-center">
      <div>
        Ваше E-mail:
      </div>
      <div class="flex gap-5 items-center">
        ivan_ivano@mail.ru

        <Button text="Изменить" @click="showModal('showEmail')"/>
      </div>
    </div>
<!--    about-->
    <div>
      <div class="input_container">
        <div>
          О себе:
        </div>
        <div class="flex flex-col gap-5">
          <textarea class="form_input w-1/2 h-64"></textarea>

          <div class="w-1/2">
            <Button text="Сохранить" class="float-right"/>
          </div>

        </div>
      </div>
      <!--    avatar-->
      <div class="input_container items-center">
        <div>
          Аватар:
        </div>
        <div>
          <Button text="Редактировать" @click="showModal('showAvatar')"/>
        </div>
      </div>

        <!--    header_fon -->
        <div class="input_container items-center">
          <div>
            Обложка:
          </div>
          <div>
            <Button text="Редактировать" @click="showModal('showObloshka')"/>
          </div>
        </div>

      <!--    web-site -->
      <div class="input_container items-center">
        <div>
          Web-сайт:
        </div>
        <div class="flex gap-5 items-center">
          <input type="text" class="form_input w-1/2 h-full">
          <Button text="Сохранить"/>
        </div>
      </div>
      <!--    Telegram -->
      <div class="input_container items-center">
        <div>
          Telegram:
        </div>
        <div class="flex gap-5 items-center">
          <input type="text" class="form_input w-1/2 h-full">
          <Button text="Сохранить"/>
        </div>
      </div>
      <!--    VK -->
      <div class="input_container items-center">
        <div>
          Вконтакте:
        </div>
        <div class="flex gap-5 items-center">
          <input type="text" class="form_input w-1/2 h-full">
          <Button text="Сохранить"/>
        </div>
      </div>
      <!--    Discord: -->
      <div class="input_container items-baseline">
        <div>
          Discord:
        </div>
        <div class="flex flex-col">
          <div class="flex gap-5 items-center">
            <input type="text" class="form_input w-1/2 h-full">
            <Button text="Сохранить"/>
          </div>
          <div class="mt-5 flex gap-9 text-theme items-center font-medium">
            <Button text="Сохранить"/>

            <RouterLink to="/logout" class="hover:text-primary transition duration-200">Выйти</RouterLink>
            <RouterLink to="/renamepass" class="hover:text-primary transition duration-200">Сбросить пароль</RouterLink>
          </div>
        </div>

      </div>
    </div>
  </div>

<!--  modal-->

  <Modal
    v-if="modalActive"
    :modalEmail="modalEmail"
    :modalName="modalName"
    :modalAvatar="modalAvatar"
    :modalObloshka="modalObloshka"
  />


</template>

<style scoped>
  .bg-panel{
    background: var(--var--bgpanelcolor);
    border-radius: 3px;
  }

  .input_container{
    display: grid;
    grid-template-columns: repeat(9,1fr);
    padding: 25px 0px;
    font-size: 20px;
    gap: 20px;
    color: var(--var--textcolor);
    font-size: 20px;
    font-weight: 500;
    border-bottom:1px solid var(--var--linecolor);
    padding-left: 30px;
  }

  .input_container:last-child{
    border-bottom: 0;
  }
  
  .input_container div:last-child{
    grid-column: span 8;
  }

  .input_container div:first-child{
    float: right;
    text-align: right;
  }
</style>