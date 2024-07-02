<script setup>

import Button from "@/components/UI components/Button.vue";

defineProps({
  auth: Boolean,
})

</script>

<template>
  <aside class="col-span-1 px-3.5 pt-3.5">
    <div class="m-auto flex flex-col">
      <RouterLink  :to="auth ? '/addpost' : '/login'">
        <Button class="w-full" text="Создать пост"/>
      </RouterLink>

      <div class="text-theme font-medium" v-for="item in 3">
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
    background-color: var(--var--bgpanelcolor);
    border: 1px solid #FFB03A;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
  }

  input[type=checkbox]:checked::after {
    background-color: #FFB03A;
  }

  .border_custom{
    border-bottom: 0.5px solid rgba(255,255,255,0.1);
  }

  aside{
    background:var(--var--bgpanelcolor);
  }
</style>