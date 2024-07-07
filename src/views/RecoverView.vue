<script setup>
  import {ref} from "vue";

  import HeaderAbsolute from "@/components/HeaderAbsolute.vue";
  import Button from "@/components/UI components/Button.vue";

  const toggleMenu = ref(false);

  const toggleRecover = () => {
    toggleMenu.value = !toggleMenu.value;
  }

</script>

<template>
  <div class="z-10 fixed left-0 top-0 full w-full h-full fon">
    <div class="container">
      <HeaderAbsolute />

      <div class="flex justify-center py-20 sm:py-52">
        <div class="form_container" v-if="!toggleMenu">
          <div class="text-theme text-2xl sm:text-3xl font-medium text-center">
            Введите ваш e-mail
          </div>

          <form @submit="toggleRecover" action="" class="flex flex-col gap-5 pt-10">
            <input class="auth_input" type="text" placeholder="ivan_ivanov" required>
            <Button text="Далее" />
          </form>

          <div class="py-2.5 w-full flex justify-center text-base sm:text-xl text-center">
            <div class="flex">
              <span class="text-theme">Еще нет акаунта?</span>
              <div class="relative ml-2.5">
                <RouterLink class="underline_anim text-primary  underline_anim" to="/signup">
                  Зарегистрироваться
                </RouterLink>
              </div>
            </div>
          </div>
        </div>


        <div class="form_container" v-if="toggleMenu">
          <div>
            <img src="/mail.svg" alt="" class="m-auto">
          </div>


          <div class="text-theme text-xl sm:text-3xl font-medium text-center pt-10">
            Письмо для сброса пароля
            было отравлено на почту
          </div>

          <RouterLink to="/login" class="pt-10">
            <Button text="Войти в аккаунт" class="w-full" />
          </RouterLink>

          <div class="py-2.5 w-full flex justify-center text-base sm:text-xl text-center">
            <div>
              <span class="thistext">Не пришло письмо?</span> <span class="thistext underline hover:opacity-90 transition cursor-pointer" @click="toggleRecover" >Отправить повторно</span>
            </div>
          </div>

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
