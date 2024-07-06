<script setup>

import Button from "@/components/UI components/Button.vue";
import InputFile from "@/components/UI components/InputFile.vue";
import CommentList from "@/components/CommentList.vue";
</script>

<template>

<!--    title-->
    <div class="flex justify-between items-center px-7 py-5 border-custom bg-panel">
      <div class="flex gap-5 items-center">
        <img src="/avatar.png" alt="" class="w-20">
        <div class="text-theme">
          <RouterLink to="/post"><h4 class="text-2xl font-medium">Ищу графического дизайнера</h4></RouterLink>
          <div class="flex gap-x-2.5 items-center text-xl">
            <span>тема из раздела</span> <span class="text-primary">графический дизайн</span>
          </div>
        </div>
      </div>

      <div class="flex justify-between items-center text-2xl  secondary_color gap-24">
        <!--          views -->
        <div>
          Просмотры <span class="text-theme">36</span>
        </div>
        <!--          comments-->
        <div>
          Комментарии <span class="text-theme">11</span>
        </div>
      </div>
    </div>

<!--    info-->
    <div class="pl-7 py-3 bg-panel mb-6 text-theme text-xl text-normal">
      🌟 В поиске талантливого графического дизайнера! 🌟

      Требуется профессионал, способный воплотить идеи в уникальные и креативные дизайн-решения. Если вы обладаете страстью к искусству и умеете превращать концепции в визуальное воплощение, мы ищем именно вас!

      Мы предлагаем:
      - Увлекательные проекты и интересные задачи
      - Гибкий график работы
      - Возможность проявить свою творческую индивидуальность
      - Дружелюбную и вдохновляющую атмосферу

      Если вы готовы воплотить свои идеи в жизнь и работать в динамичной команде, отправьте нам свое портфолио и резюме. Мы ждем именно вас, чтобы создавать вместе удивительные дизайн-проекты! 🎨✨

      <div class="mt-10">

      </div>
    </div>

<!--  add comment-->
  <form action="" class="flex flex-col gap-5 bg-panel mb-6 px-7 py-5">
    <label for="comment" class="text-theme font-medium text-2xl">Оставить комментарий</label>

    <input type="text" name="comment" class="form_input">

    <div class="flex gap-5">
      <Button text="Опубликовать" class="text-xl"/>

      <InputFile text="Прикрепить файл"/>
    </div>
  </form>

<!--  comment list-->
  <div class="bg-panel pl-7 py-4">
    <h4 class="text-2xl text-theme font-medium">Комментарии</h4>
  </div>

  <CommentList/>


</template>

<style scoped>
  .bg-panel{
    background:var(--var--bgpanelcolor);
  }

  .border-custom{
    border-bottom: 1px solid var(--var--linecolor);
  }

  .secondary_color{
    color:var(--var--secondarycolor)
  }
</style>