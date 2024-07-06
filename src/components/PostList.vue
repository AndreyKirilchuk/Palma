<script setup>
  import {reactive} from "vue";

  import Post from "@/components/Post.vue";

  const items = reactive([
    {
      id: 1,
      title: "Заголовок статьи 1",
      imageUrl: "/avatar.png",
      author: "Автор 1",
      date: "2023-10-26",
      views: 1234,
      comments: 5
    },
    {
      id: 2,
      title: "Заголовок статьи 2",
      imageUrl: "/avatar.png",
      author: "Автор 2",
      date: "2023-10-25",
      views: 5678,
      comments: 10
    },
    {
      id: 3,
      title: "Заголовок статьи 3",
      imageUrl: "/avatar.png",
      author: "Автор 3",
      date: "2023-10-24",
      views: 9012,
      comments: 15
    }
  ]);
</script>

<template>
  <!--  container_list-->
  <div class="post_list_container w-full flex flex-col" v-auto-animate>
    <Post
        v-for="item in items"
        :key="item.id"
        :id="item.id"
        :title="item.title"
        :imageUrl="item.imageUrl"
        :author="item.author"
        :date="item.date"
        :views="item.views"
        :comments="item.comments"
    />
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