<script setup>

  import HeaderAbsolute from "@/components/HeaderAbsolute.vue";
  import Button from "@/components/UI components/Button.vue";

</script>

<template>
  <div class="z-10 fixed left-0 top-0 full w-full h-full fon">
    <div class="container">
      <HeaderAbsolute />

      <div class="flex justify-center py-52">
        <div class="form_container">
          <div class="text-theme text-3xl font-medium text-center">
            Войдите в аккаунт!
          </div>

          <form action="/login" class="flex flex-col gap-5 pt-10">
            <input class="auth_input" type="text" placeholder="Логин" required>
            <input class="auth_input" type="password" placeholder="Пароль" required>
            <Button text="Войти" />
          </form>

          <div class="py-2.5 w-full text-xl text-center">
            <div class="flex">
              <span class="text-theme ml-10">Еще нет акаунта?</span>
              <div class="relative ml-5">
                <RouterLink class="underline_anim text-primary  underline_anim" to="/signup">
                    Зарегистрироваться
                </RouterLink>
              </div>
            </div>
            <div>
              <span class="thistext">Забыли пароль?</span> <RouterLink class="thistext mx-2 underline hover:opacity-90 transition" to="/recover">Восстановить</RouterLink>
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
