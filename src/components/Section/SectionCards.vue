<script setup>
import items from '../../storeItems.js';
import { ref } from 'vue'
const arr = ref(items.items);

const props = defineProps({
  value: {
    type: Boolean,
    default: false,
  }
})
</script>

<template>
  <div v-for="item in arr" :key="item.id"
  :class="{shadow: item.checked}"
  class="w-11/12 h-fit pb-6 bg-white ml-5 mt-5 rounded-2xl md:w-[28rem] lg:w-[29.8rem]">
<!-- контейнер -->
    <div class="flex relative">
      <!-- 1 потомок в столбец -->
      <div class="ml-4 flex flex-col items-start">
              <!-- Временной интервал -->
        <p class="text-[13px] leading-4 mt-6 font-normal text-gray-500">{{ item.timeInterval }}</p>
              <!-- Подзаголовок -->
        <h5 class="font-medium text-xl">{{ item.title }}</h5>
              <!-- Текст -->
        <p class="mt-2 w-[19.5rem] sm:w-[20.3rem] text-sm text-left text-gray-500">{{ item.text }}</p>
      <!-- 1 дочерний потомок в строчку -->
          <div class="flex space-x-2 mt-4">
              <!-- галка -->
            <img src="../../assets/icons/Vector.svg"/> 
              <!-- 1 бонус (текст) -->
            <p class="text-sm">{{ item.pointOne }}</p>
          </div>
      <!-- 2 дочерний потомок в строчку -->
          <div class="flex space-x-2 mt-2">
              <!-- галка -->
            <img src="../../assets/icons/Vector.svg"/> 
              <!-- 2 бонус (текст) -->
            <p class="text-sm">{{ item.pointTwo }}</p>
          </div>
      <!-- 3 дочерний потомок с условием, если нету props.value, то значение берем checked из storeItems.js  -->
              <!-- переключалка -->
          <div v-if="!props.value" class="mt-[18px]">
            <label class="relative inline-flex items-center cursor-pointer">
              <input type="checkbox" id="checkbox" v-model="item.checked"  class="sr-only peer">
              <div class="w-11 h-6 bg-gray-200 peer-focus:outline-none peer-focus:ring-2 peer-focus:ring-sky-500 dark:peer-focus:ring-blue-800 rounded-full peer dark:bg-gray-700 peer-checked:after:translate-x-full peer-checked:after:border-white after:content-[''] after:absolute after:top-[2px] after:left-[2px] after:bg-white after:border-gray-300 after:border after:rounded-full after:h-5 after:w-5 after:transition-all dark:border-gray-600 peer-checked:bg-blue-600"></div>
              <span class="ml-3 text-sm font-normal text-black">Уже получают {{ item.count }} человек</span>
            </label>
          </div>
      <!-- 3 дочерний потомок с условием, если есть props.value, то применяем его значение на всех элементах -->
              <!-- переключалка -->
          <div v-else class="mt-[18px]">
            <label class="relative inline-flex items-center cursor-pointer">
              <input type="checkbox" id="checkbox" v-model="props.value"  class="sr-only peer">
              <div class="w-11 h-6 bg-gray-200 peer-focus:outline-none peer-focus:ring-2 peer-focus:ring-sky-500 dark:peer-focus:ring-blue-800 rounded-full peer dark:bg-gray-700 peer-checked:after:translate-x-full peer-checked:after:border-white after:content-[''] after:absolute after:top-[2px] after:left-[2px] after:bg-white after:border-gray-300 after:border after:rounded-full after:h-5 after:w-5 after:transition-all dark:border-gray-600 peer-checked:bg-blue-600"></div>
              <span class="ml-3 text-sm font-normal text-black">Уже получают {{ item.count }} человек</span>
            </label>
          </div>
        </div>
      <!-- 2 потомок -->
      <!-- картинка в верхнем правом углу карточки -->
        <img class="absolute left-3/4 w-10 h-10 mt-6 ml-6 md:w-20 md:h-20 md:ml-1 lg:ml-6" :src='item.svg' alt="klerk-logo"/>
    </div>
  
  </div>
</template>

<style scoped>
.shadow {
  box-shadow: 0px 8px 16px rgba(0, 0, 0, 0.08);
}
</style>
