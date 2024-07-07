<script setup>
  import { inject } from "vue";

  const { closeBurger} = inject("burger")

  import Aside from './Aside.vue';
  import Search from "@/components/UI components/Search.vue";

  defineProps({
    burgerActive: Boolean,
    auth: Boolean
  })
</script>

<template>
  <div class="burger_fon" @click="closeBurger" v-if="burgerActive"/>


  <div class="burger" :class="{'active': burgerActive}">
    <Aside :auth="auth" />
  </div>

</template>

<style scoped>
.burger_fon{
    position: fixed;
    left: 0;
    top: 0;
    background: 0;
    width: 100%;
    height: 100%;
    z-index: 500;
  }

  .burger{
    position: fixed;
    top: 0;
    left: 0;
    transform: translateX(-100%);
    width: 260px;
    background: var(--var--burgercolor);
    transition: 0.3s ease-in-out;
    height: 100%;
    z-index: 500;
    border-right: 1px solid var(--var--linecolor);
    padding: 25px 15px 0px ;
  }

  .burger.active{
    transform: translateX(0);
  }

</style>