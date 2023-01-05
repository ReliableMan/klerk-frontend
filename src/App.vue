<script setup>
import Navbar from './components/Navbar/Navbar.vue';
import SectionOne from './components/Section/SectionOne.vue';

</script>

<template>
<!-- лого и навигация -->
  <navbar/>
<!-- заголовок -->
  <div class="mx-auto text-center sm:pt-6">
    <h1 class="text-[32px] font-medium leading-[4.5rem] text-center tracking-[-.01em] sm:text-[56px]">Подписки «Клерка»</h1>
<!-- постраничная навигация -->
    <nav class="flex justify-center pt-7 space-x-5 w-auto bg-white text-gray-600 text-base font-normal">
      <a href="#" aria-current="page" 
        class="pb-4 hover:border-b  hover:border-blue-700  hover:text-blue-700 focus:z-10 focus:border-b-2 focus:border-blue-700 focus:text-blue-700">
          Рассылки
      </a>
      <a href="#" 
        class="pb-4 hover:border-b hover:border-blue-700 hover:text-blue-700 focus:z-10 focus:border-b-2 focus:border-blue-700 focus:text-blue-700">
          Соцсети
      </a>
      <a href="#" 
        class="pb-4 hover:border-b hover:border-blue-700 hover:text-blue-700 focus:z-10 focus:border-b-2 focus:border-blue-700 focus:text-blue-700">
        Мессенджеры
      </a>
    </nav>
<!-- контентная часть -->
    <section-one/>
<!-- футер с типчиком -->
    <div class="flex justify-center mb-11">
      <img src="./assets/images/man.svg" alt="klerk-man"/>
    </div>

  </div>
</template>

<style scoped>
.active {
  color: rgb(59 130 246)
}
 .activeLink {
  display: block;
  width: 78px;
  height: 2px;
  background-color: #5A8CF1;
  margin-top: 18px
 }
</style>
