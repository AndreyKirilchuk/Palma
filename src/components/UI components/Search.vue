<script setup>
  import {inject} from "vue";

  const { closeBurger } = inject('burger');
</script>

<template>
  <div class="flex flex-nowrap items-center gap-x-3.5 rounded-sm bg-white py-2 sm:py-2.5 px-3.5 search">
    <RouterLink to="/search" @click="closeBurger">
      <svg width="18" height="19" viewBox="0 0 18 19" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path class="search" d="M18 17.9758L12.972 12.9557C14.1803 11.5074 14.7828 9.64976 14.6542 7.76924C14.5256 5.88872 13.6759 4.13008 12.2817 2.85916C10.8876 1.58825 9.05634 0.902922 7.16898 0.94574C5.28163 0.988557 3.48346 1.75623 2.14855 3.08905C0.813648 4.42187 0.0447792 6.21723 0.00189494 8.10165C-0.0409893 9.98606 0.645413 11.8144 1.91831 13.2064C3.19121 14.5984 4.95259 15.4468 6.83605 15.5752C8.71952 15.7036 10.58 15.102 12.0306 13.8956L17.0586 18.9158L18 17.9758ZM1.35538 8.27983C1.35538 7.09656 1.70681 5.93986 2.36522 4.95601C3.02364 3.97216 3.95947 3.20534 5.05438 2.75252C6.14928 2.2997 7.35409 2.18122 8.51643 2.41207C9.67878 2.64291 10.7465 3.21271 11.5845 4.04941C12.4225 4.88611 12.9932 5.95212 13.2244 7.11266C13.4556 8.27319 13.3369 9.47611 12.8834 10.5693C12.4299 11.6625 11.6618 12.5969 10.6765 13.2543C9.69106 13.9117 8.53256 14.2625 7.34744 14.2625C5.75879 14.2608 4.23571 13.6299 3.11236 12.5083C1.98901 11.3867 1.35714 9.866 1.35538 8.27983Z" fill="#222222" fill-opacity="0.3"/>
      </svg>
    </RouterLink>

    <input type="search" placeholder="Поиск" class="text-base search w-full"/>
  </div>
</template>

<style scoped>
  .search{
    background: var(--var--bgsearch);
    color: var(--var--btncolor);
    fill: var(--var--searchsvgcolor);
  }



  .search::placeholder{
    color: var(--var--btncolor);
  }

</style>