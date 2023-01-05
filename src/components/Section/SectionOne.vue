<script setup>
import SectionCards from './SectionCards.vue';
import { ref } from 'vue'
const value = ref(false);
</script>

<template>
  <div class="flex justify-center">
    <div 
    :class="{allGray: value}"
    class="w-full h-fit pb-8 sm:pb-12 bg-gray-100 items-center sm:rounded-2xl lg:w-[64rem] lg:h-[50rem] md:h-fit">
    <!-- Подзаголовок на сером фоне -->
      <h6 class="ml-4 mt-8 text-left font-medium text-2xl sm:text-center tracking-[-.01em]">Выберите рассылки, которые подходят именно вам</h6>
       <!--Инпут и кнопка -->
      <div class="flex mt-6 sm:justify-center md:justify-center ">
         <input type="email" name="email" class="ml-4 w-11/12 lg:w-[48rem] h-[3.5rem] py-4 shadow-sm border-slate-300 placeholder-slate-400 focus:outline-none focus:border-sky-500 focus:ring-sky-500 focus:text-xl block rounded-md sm:text-sm focus:ring-1 md:w-6/12" placeholder="Электронная почта" />
         <!--кнопка версия для ПК -->
         <button class="desktop relative right-7 h-[3.5rem] rounded-[100px] px-8 py-4 text-base font-normal text-white bg-blue-500 hover:bg-blue-600">Подписаться</button>
         <!-- кнопка для мобилки -->
         <button class="mobile relative right-5 h-[3.5rem] rounded-[100px] px-4 py-4 text-base font-normal text-white bg-blue-500 hover:bg-blue-600">
          <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7"></path>
          </svg>
        </button>

       </div>

       <!-- Переключалка для рассылок с текстом  -->
        <div class="mt-4 ml-[17px] flex lg:justify-start lg:ml-16 md:justify-center sm:justify-center">
          <label class="relative inline-flex items-center cursor-pointer">
          <input type="checkbox" value="" v-model='value' class="sr-only peer">
          <div class="w-11 h-6 bg-gray-200 peer-focus:outline-none peer-focus:ring-2 peer-focus:ring-sky-500 dark:peer-focus:ring-blue-800 rounded-full peer dark:bg-gray-700 peer-checked:after:translate-x-full peer-checked:after:border-white after:content-[''] after:absolute after:top-[2px] after:left-[2px] after:bg-white after:border-gray-300 after:border after:rounded-full after:h-5 after:w-5 after:transition-all dark:border-gray-600 peer-checked:bg-blue-600"></div>
          <span class="ml-3 text-sm font-normal text-black ">Подписаться на все рассылки</span>
          </label>
        </div>
        <!-- карточки -->
          <div class="flex flex-wrap sm:justify-center md:justify-center">
            <section-cards :value="value"/>  
          </div>
    </div>
  </div>
</template>

<style scoped>
input::placeholder {
  padding: 16px 0px 16px 16px;
  font-style: normal;
  font-weight: 400;
  font-size: 16px;
  line-height: 24px;
  color: #666666;
}
.allGray{
  background-color: #e5e7eb;
}

@media only screen and (min-device-width: 320px) and (max-device-width: 480px){ 
  .desktop { 
    display: none; 
  }
}
@media only screen and (min-device-width: 481px) {
  .mobile {
    display: none; 
  }
}

</style>
