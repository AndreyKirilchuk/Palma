<script setup>

</script>

<template>
  <div class="bg-panel flex flex-col">
<!--    name-->
    <div class="input_container" v-for="item in 10">
      <div>
        Ваше имя:
      </div>
      <div>
        Иван иванов
      </div>
    </div>
<!--    email-->
    <div>
      <div>

      </div>
      <div>

      </div>
    </div>

    <div>
      <div>

      </div>
      <div>

      </div>
    </div>

    <div>
      <div>

      </div>
      <div>

      </div>
    </div>

    <div>

    </div>
  </div>
</template>

<style scoped>
  .bg-panel{
    background: var(--var--bgpanelcolor);
  }

  .input_container{
    display: grid;
    grid-template-columns: repeat(9,1fr);
    padding: 25px 0px;
    font-size: 20px;
    border-radius: 10px;
    gap: 20px;
    color: var(--var--textcolor);
    font-size: 20px;
    font-weight: 500;
    border-bottom:1px solid var(--var--linecolor);
  }

  .input_container:last-child{
    border-bottom: 0;
  }


  .input_container div:last-child{
    grid-column: span 8;
  }

  .input_container div:first-child{
    float: right;
    text-align: right;
  }

</style>