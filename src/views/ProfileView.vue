<script setup>
  import {ref} from "vue";

  import PostList from "@/components/PostList.vue";
  import Button from "@/components/UI components/Button.vue";
  import CommentList from "@/components/CommentList.vue";

  const activeButton = ref('posts');
  const activeLike = ref('');
</script>

<template>
  <div>
<!--    top panel-->
    <div class="tracking-wide bg_panel mb-5">
      <img src="/profile_header.png" alt="">

      <div class="border_custom grid grid-cols-2 px-7 py-5">

        <div class="flex items-center gap-x-5">
<!--          avatar-->
          <img src="/avatar.png" alt="" class="w-20">
<!--          name-->
          <div class="text-theme ">
            <h3 class="text-3xl font-semibold">Иванов Иван</h3>
            <span class="text-xl font-regular">в сети</span>
          </div>
        </div>
        <div class="flex justify-between items-center text-2xl  secondary_color">
<!--          reputation-->
          <div>
            Репутация <span class="text-theme">0</span>
          </div>
<!--          count posts-->
          <div>
            Посты <span class="text-theme"> 20 </span>
          </div>
<!--          comments-->
          <div>
            Комментарии <span class="text-theme">11</span>
          </div>
        </div>
      </div>


      <div class="flex justify-between items-center px-7 py-5">
<!--        date make profile-->
        <div class="">
          <span class="secondary_color">Профиль создан</span> <span class="text-theme ml-2">16 мая 2024</span>
        </div>
<!--        profile_settings link ( if auth )    -->
        <RouterLink to="/profile/settings" v-if="1 === 2">
          <Button text="Редактировать" class="max-w-52 px-5 py-1.5" />
        </RouterLink>
        <!--        buttons like        -->
        <div class="flex justify-between items-center bg-primary rounded-sm" v-if="1 === 1">
          <div class="like_container" :class="{ active: activeLike === 'like' }" @click="activeLike = 'like'">
            <svg width="22" height="20" viewBox="0 0 22 20" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path d="M22 9C22 8.46957 21.7893 7.96086 21.4142 7.58579C21.0391 7.21071 20.5304 7 20 7H13.68L14.64 2.43C14.66 2.33 14.67 2.22 14.67 2.11C14.67 1.7 14.5 1.32 14.23 1.05L13.17 0L6.59 6.58C6.22 6.95 6 7.45 6 8V18C6 18.5304 6.21071 19.0391 6.58579 19.4142C6.96086 19.7893 7.46957 20 8 20H17C17.83 20 18.54 19.5 18.84 18.78L21.86 11.73C21.95 11.5 22 11.26 22 11V9ZM0 20H4V8H0V20Z" fill="#222222" fill-opacity="0.3"/>
            </svg>
          </div>
          <div class="border_custom_left like_container" :class="{ active: activeLike === 'dislike' }" @click="activeLike = 'dislike'">
            <svg width="22" height="20" viewBox="0 0 22 20" fill="none" xmlns="http://www.w3.org/2000/svg">
              <path opacity="0.5" d="M22 11C22 11.5304 21.7893 12.0391 21.4142 12.4142C21.0391 12.7893 20.5304 13 20 13H13.68L14.64 17.57C14.66 17.67 14.67 17.78 14.67 17.89C14.67 18.3 14.5 18.68 14.23 18.95L13.17 20L6.59 13.42C6.22 13.05 6 12.55 6 12V2C6 1.46957 6.21071 0.960861 6.58579 0.585787C6.96086 0.210714 7.46957 0 8 0H17C17.83 0 18.54 0.5 18.84 1.22L21.86 8.27C21.95 8.5 22 8.74 22 9V11ZM0 0H4V12H0V0Z" fill="#222222" fill-opacity="0.3"/>
            </svg>
          </div>
        </div>
      </div>
    </div>


<!--    bottom panel-->
    <div class="grid grid-cols-3 gap-5 tracking-wide">
      <div class="col-span-2">
<!--        buttons-->
        <div class="p-1 grid grid-cols-2 buttons_container mb-3.5 bg_panel text-lg">
          <button :class="{ active: activeButton === 'posts' }" @click="activeButton = 'posts'">Посты</button>

          <button :class="{ active: activeButton === 'comments' }" @click="activeButton = 'comments'">Комментарии</button>
        </div>

<!--        posts-->
        <PostList v-if="activeButton === 'posts'" />

<!--        comments-->
        <CommentList v-if="activeButton === 'comments'" />
      </div>

<!--      about profile -->
      <div class="bg_panel p-7  text-xl about_profile h-fit">
        <p>О себе</p>
        <span>Креативный директор диджитал агенства W. Ищу команду и крутые идеи  </span>
        <p>Телефон</p>
        <span>+7 987 654 32 10</span>
        <p>Дата рождения</p>
        <span>8 мая 2000г</span>
        <p>E-mail</p>
        <span>ivanov_inan@gmail.com</span>
        <p>Telegram</p>
        <span>@ivanov_inan</span>
        <p>Web-сайт</p>
        <span>w-agency.ru</span>
      </div>
    </div>
  </div>
</template>

<style scoped>
.border_custom{
  border-bottom: 0.5px solid var(--var--linecolor);
}

.secondary_color{
  color:var(--var--secondarycolor)
}

.border_custom_left{
  border-left: 0.1px solid var(--var--borederlikecolor);
}

.bg_panel{
  background: var(--var--bgpanelcolor);
}

.buttons_container{
  border-radius: 3px;
  background: var(--var--bgtogglebuttoncolor);
}

.buttons_container button.active{
  background:#FFB03A;
  color: var(--var--texttogglebuttoncolor);
}

.buttons_container button{
  color: var(--var--textcolor);
  border-radius: 3px;
  padding: 4px 0px;
  font-weight: 600;
}

.like_container{
  padding: 10px 20px;
  transition: 0.3s;
  cursor: pointer;
}

.like_container:hover path{
  transition: 0.3s;
  fill-opacity:1;
}


.like_container.active path{
  fill-opacity: 1;
}

.about_profile p{
  color: var(--var--secondarycolor);
}

.about_profile span{
  color: var(--var--textcolor);
}
</style>