<script setup>
  defineProps({
    id: Number,
    title: String,
    imageUrl: String,
    author: String,
    date: String,
    views: Number,
    comments: Number,
  })
</script>

<template>
  <div class="flex justify-between items-center py-5 px-7 border-b border_custom">
    <!--      left post-->
    <div class="flex gap-5 items-center">
      <img :src="imageUrl" alt="avatar" class="w-14">
      <div class="text-theme">
        <RouterLink to="/post"><h4 class="text-xl font-medium hover:text-primary transition duration-200">{{ title }}</h4></RouterLink>
        <div class="flex gap-x-2.5">
          <span>{{ author }}</span> <span>{{ date }}</span>  <div class="flex gap-x-1"> <img src="/eye.svg" alt=""> <span>{{ views }}</span> </div> <div class="flex gap-x-1"> <img src="/message.svg" alt=""> <span> {{ comments }} </span> </div>
        </div>
      </div>
    </div>
    <!--      right post-->
    <div>

    </div>
  </div>
</template>

<style scoped>

</style>