<script setup>
  defineProps({
    path: String,
  })
</script>

<template>
  <div class="pt-5 text-xl">

    <!-- main page-->
    <div class="relative">
      <RouterLink to="/" class="underline_animWhite">Главная </RouterLink>
    </div>

    <!-- arrow-->
    <svg width="7" height="12" viewBox="0 0 7 12" fill="none" xmlns="http://www.w3.org/2000/svg">
      <path d="M1 1L6 6L1 11" stroke="white" stroke-linecap="round"/>
    </svg>

    <!-- profile page -->
    <div v-if="path === '/profile'">
      <span class="text">Мой профиль</span>
    </div>

    <!-- add_post page -->
    <div v-if="path === '/addpost'">
      <span class="text">Создать пост</span>
    </div>

    <!-- redact_settings page -->
    <div v-if="path === '/profile/settings'">
      <div class="relative">
        <RouterLink class="underline_animWhite" to="/profile">
          Профиль
        </RouterLink>
      </div>

      <svg width="7" height="12" viewBox="0 0 7 12" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M1 1L6 6L1 11" stroke="white" stroke-linecap="round"/>
      </svg>

      <span class="text">
        Настройки профиля
      </span>
    </div>


  </div>
</template>

<style scoped>
    a{
      color:var(--var--textcolor);
    }

    div{
      display: flex;
      gap: 10px;
      align-items: center;
    }

    svg path{
      stroke: var(--var--textcolor);
    }

    .text{
      color:#FFB03A;
    }
</style>