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
  <div class="flex flex-col sm:flex-row justify-between gap-5 sm:items-center py-5 px-5 sm:px-7 border-b border_custom">
    <!--      left post-->
    <div class="flex gap-2.5 sm:gap-5 items-center">
      <img :src="imageUrl" alt="avatar" class="w-12 sm:w-14">
      <div class="text-theme">
        <RouterLink to="/post"><h4 class="text-base sm:text-xl font-medium hover:text-primary transition duration-200">{{ title }}</h4></RouterLink>
        <div class="flex gap-x-2.5 text-sm sm:text-base">
          <span class="m">{{ author }}</span> <span>{{ date }}</span>  <div class="flex gap-x-1"> <img src="/eye.svg" alt=""> <span>{{ views }}</span> </div> <div class="flex gap-x-1"> <img src="/message.svg" alt=""> <span> {{ comments }} </span> </div>
        </div>
      </div>
    </div>
    <!--      right post-->
    <div>
      фыв
    </div>
  </div>
</template>

<style scoped>

</style>