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
    },
    {
      id: 4,
      title: "Заголовок статьи 4",
      imageUrl: "/avatar.png",
      author: "Автор 4",
      date: "2023-10-23",
      views: 3456,
      comments: 20
    },
    {
      id: 5,
      title: "Заголовок статьи 5",
      imageUrl: "/avatar.png",
      author: "Автор 5",
      date: "2023-10-22",
      views: 7890,
      comments: 25
    },
    {
      id: 6,
      title: "Заголовок статьи 6",
      imageUrl: "/avatar.png",
      author: "Автор 6",
      date: "2023-10-21",
      views: 12345,
      comments: 30
    },
    {
      id: 7,
      title: "Заголовок статьи 7",
      imageUrl: "/avatar.png",
      author: "Автор 7",
      date: "2023-10-20",
      views: 56789,
      comments: 35
    },
    {
      id: 8,
      title: "Заголовок статьи 8",
      imageUrl: "/avatar.png",
      author: "Автор 8",
      date: "2023-10-19",
      views: 90123,
      comments: 40
    },
    {
      id: 9,
      title: "Заголовок статьи 9",
      imageUrl: "/avatar.png",
      author: "Автор 9",
      date: "2023-10-18",
      views: 34567,
      comments: 45
    },
    {
      id: 10,
      title: "Заголовок статьи 10",
      imageUrl: "/avatar.png",
      author: "Автор 10",
      date: "2023-10-17",
      views: 78901,
      comments: 50
    },
    {
      id: 11,
      title: "Заголовок статьи 11",
      imageUrl: "/avatar.png",
      author: "Автор 11",
      date: "2023-10-16",
      views: 123456,
      comments: 55
    },
    {
      id: 12,
      title: "Заголовок статьи 12",
      imageUrl: "/avatar.png",
      author: "Автор 12",
      date: "2023-10-15",
      views: 567890,
      comments: 60
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