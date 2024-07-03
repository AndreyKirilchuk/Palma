<script setup>

</script>

<template>
  <!--  container_list-->
  <div class="post_list_container w-full flex flex-col">
    <!--    post-->
    <div class="flex justify-between items-center py-5 px-7 border-b border_custom" v-for="item in 10">
      <!--      left post-->
      <div class="flex gap-5 items-center">
        <img src="/avatar.png" alt="">
        <div class="text-theme">
          <h3 class="text-xl font-medium">Ищу графического дизайнера</h3>
          <div class="flex gap-x-2.5">
            <span>Иванов иван</span> <span>Сегодня в 15:04</span>  <div class="flex gap-x-1"> <img src="/eye.svg" alt=""> <span>34</span> </div> <div class="flex gap-x-1"> <img src="/message.svg" alt=""> <span>2</span> </div>
          </div>
        </div>
      </div>
      <!--      right post-->
      <div>
      фывфыв
      </div>
    </div>
  </div>

  <div>

  </div>
</template>

<style scoped>
  .border_custom {
    border-bottom: 0.5px solid var(--var--linecolor);
  }

  .border_custom:last-child{
    border-bottom: 0;
  }

  .post_list_container{
    background: var(--var--bgpanelcolor);
  }


</style>