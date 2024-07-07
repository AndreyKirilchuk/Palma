<script setup>

  import Button from "@/components/UI components/Button.vue";
  import Search from "@/components/UI components/Search.vue";
  import {inject} from "vue";

  defineProps({
    auth: Boolean,
  })

  const { closeBurger } = inject('burger');

</script>

<template>
  <aside class="col-span-1  md:px-1 xl:px-3.5 pt-3.5 h-fit">

    <Search class="block md:hidden mb-4"/>

    <div class="m-auto flex flex-col h-fit">
      <RouterLink  :to="auth ? '/addpost' : '/login'" @click="closeBurger">
        <Button class="w-full px-0" text="Создать пост"/>
      </RouterLink>

      <div class="border_custom_container text-theme font-medium" v-for="item in 3">
        <div class="text-xl pt-5">Интересное</div>

        <div class="border_custom flex flex-col gap-3.5 py-5">
          <div class="flex items-center gap-x-2.5" v-for="item in 5">
            <input type="checkbox" >
            <label>Подкатегория</label>
          </div>

        </div>

      </div>
    </div>
  </aside>
</template>

<style scoped>
  input[type=checkbox] {
    position: relative;
    width: 20px;
    height: 20px;
  }

  input[type=checkbox]::before {
    content: "";
    position: absolute;
    border-radius: 3px;
    width: 20px;
    height: 20px;
    background-color: #401C56;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }

  input[type=checkbox]::after {
    cursor: pointer;
    content: "";
    position: absolute;
    border-radius: 3px;
    width: 20px;
    height: 20px;
    border: 1px solid #FFB03A;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }

  @media(min-width: 768px){
    input[type=checkbox]::after {
      background-color: var(--var--bgpanelcolor);
    }
  }

  input[type=checkbox]:checked::after {
    background-color: #FFB03A;
  }

  .border_custom{
    border-bottom: 0.5px solid var(--var--linecolor);
  }

  @media(min-width:768px) {
    aside {
      background: var(--var--bgpanelcolor);
    }
  }

    .border_custom_container:last-child div{
      border-bottom: 0;
    }

</style>