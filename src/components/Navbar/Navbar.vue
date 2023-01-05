<script setup>
import logo from '../../assets/images/klerk.svg'
</script>

<template>
  <div class="pt-12 flex justify-center">
    <img class="h9 w20" :src="logo" alt="klerk-logo"/>
  </div>
    <!-- навигация на мобилке(главная - рассылки - хлебные крошки) -->
    <nav class="breadcrumbMobile pt-2" aria-label="Breadcrumb">
      <ul class="flex flex-wrap list-none pt-[30px] pl-2 m-0 justify-center text-gray-300 ">
        <li><a class="underline" href="#">Главная</a></li>
        <li><a class="underline" href="#">Рассылки</a></li>
        <li><a class="underline" href="#">Хлебные крошки</a></li>
      </ul>
    </nav>
    <!-- навигация на пк(хлебные крошки - хлебные крошки - хлебные крошки) -->
    <nav class="breadcrumb pt-2" aria-label="Breadcrumb">
      <ul class="flex flex-wrap list-none pt-7 pl-2 m-0 justify-center text-gray-300 ">
        <li v-for="n in 3"><a class="underline" href="#">Хлебные крошки</a></li>
      </ul>
    </nav>
</template>

<style scoped>
.breadcrumb li:not(:last-child)::after {
    margin: 0 .5rem;
    content: "→";
}
.breadcrumbMobile li:not(:last-child)::after {
    margin: 0 .5rem;
    content: "→";
}
@media only screen and (min-device-width: 320px) and (max-device-width: 480px){ 
  .breadcrumb { 
    display: none; 
  }
}
@media only screen and (min-device-width: 481px) {
  .breadcrumbMobile {
    display: none; 
  }
}
</style>
