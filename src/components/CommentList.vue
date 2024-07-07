<script setup>

</script>

<template>
  <div class="сomment_list_container w-full flex flex-col">
    <!--    comment-->
    <div class="grid grid-cols-1 gap-y-5 sm:grid-cols-6 justify-between items-center py-5 px-7 border-b border_custom" v-for="item in 12">
      <!--      left comment-->
      <div class="flex sm:flex-nowrap col-span-5 gap-5 items-center">
        <img src="/avatar.png" alt="" class="w-14">
        <div class="text-theme">
          <h4 class="text-base lg:text-xl font-medium">Привет! Я графический дизайнер с большим опытом, посмотри профиль, там есть контакты и мои работы</h4>
          <div class="flex gap-x-2.5">
            <span class="m">Иван иванов</span> <span>22-12-2023</span>  <div class="flex gap-x-1"> <img src="/eye.svg" alt=""> <span>12</span> </div> <div class="flex gap-x-1"> <img src="/message.svg" alt=""> <span> 12</span> </div>
          </div>
        </div>
      </div>
      <!--      right comment -->
      <div class="text-lg text-right lg:text-xl text-secondary cursor-pointer">
        <RouterLink to="/post">
          Ответить
        </RouterLink>
      </div>
    </div>
  </div>
</template>

<style scoped>
  .сomment_list_container{
    background: var(--var--bgpanelcolor);
  }

  .border_custom {
    border-bottom: 0.5px solid var(--var--linecolor);
  }

  .border_custom:last-child{
    border-bottom: 0;
  }

  .text-secondary{
    color: var(--var--secondarycolor);
  }
</style>