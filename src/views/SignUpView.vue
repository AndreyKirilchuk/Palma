<script setup>
  import {ref} from "vue";

  import HeaderAbsolute from "@/components/HeaderAbsolute.vue";
  import Button from "@/components/UI components/Button.vue";

  const message = ref(false);
  const mail = ref(false);

  const toggleMessage = () => {
    message.value = !message.value;

    setTimeout( () => {
      mailAccept()
    },2500);
  }

  // When confirming email
  const mailAccept = () => {
    mail.value = true;
  }

</script>

<template>
  <div class="z-10 fixed left-0 top-0 full w-full h-full fon">
    <div class="container">
      <HeaderAbsolute />

      <!--signForm-->
      <div class="flex justify-center py-20 sm:py-52">
        <div class="form_container" v-if="!message && !mail">
          <div class="text-theme text-2xl sm:text-3xl font-medium text-center">
            Создайте аккаунт!
          </div>

          <form action="" @submit="toggleMessage" class="flex flex-col gap-5 pt-10">
            <input class="auth_input" type="email" placeholder="Почта" required>
            <input class="auth_input" type="text" placeholder="Логин" required>
            <input class="auth_input" type="password" placeholder="Пароль" required>
            <input class="auth_input" type="password" placeholder="Повторите пароль" required>
            <Button text="Зарегестрироваться" />
          </form>

          <div class="py-2.5 w-full flex justify-center text-base sm:text-xl text-center">
            <div class="flex">
              <span class="text-theme">Уже есть аккаунт?</span>
              <div class="relative ml-5">
                <RouterLink class="underline_anim text-primary  underline_anim" to="/login">
                  Войти
                </RouterLink>
              </div>
            </div>
          </div>
        </div>

        <!--signMessage-->
        <div class="form_container" v-if="message && !mail">
          <div>
            <img src="/mail.svg" alt="" class="m-auto">
          </div>


          <div class="text-theme text-xl sm:text-3xl font-medium text-center pt-10">
            Письмо с подтверждением было
            отравлено на почту
          </div>

          <div class="py-2.5 w-full flex justify-center text-base sm:text-xl text-center">
            <div>
              <span class="thistext">Не пришло письмо?</span> <span class="thistext mx-2 underline hover:opacity-90 transition cursor-pointer" @click="toggleMessage" >Отправить повторно</span>
            </div>
          </div>
        </div>

        <div class="form_container" v-if="mail">
          <div>
            <img src="/check_mark.svg" alt="" class="m-auto">
          </div>


          <div class="text-theme text-xl sm:text-3xl font-medium text-center pt-10">
            Почта была успешно подтверждена!
          </div>

          <RouterLink to="/login" class="pt-10">
            <Button text="Войти в аккаунт" class="w-full" />
          </RouterLink>
        </div>

      </div>
    </div>
  </div>
</template>

<style scoped>
.thistext{
  color: var(--var--secondarycolor);
}

.form_container{
  max-width: 450px;
  width: 450px;
  display: flex;
  flex-direction: column;
  margin: 0 auto;
}
</style>