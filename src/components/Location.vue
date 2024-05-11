<script setup>
import Rating from './Rating.vue';
const props = defineProps([
    'title', 'image', 'location', 'price', 'rating', 'time'
])
</script>

<template>
      <article class="pb-5 max-w-sm transform duration-500 hover:-translate-y-1 cursor-pointer border rounded group">
      <div class="max-h-125 overflow-hidden">
        <img class="h-[350px] transform duration-500 group-hover:scale-105 object-cover" :src="image" :alt="title">
      </div>
      <div class="mx-3">
      <div class="flex justify-between my-5">
        <div class="text-orange-500 text-base font-semibold">{{ location }}</div>
        <div class="text-base text-right"><span class="font-bold">${{ price }}</span>/Day</div>
      </div>
        <h2 class="font-bold text-2xl">{{ title }}</h2>
        <div class="flex justify-between items-center mt-3">
          <div class="text-base uppercase font-semibold text-gray-500"> {{ time }} Days Tour</div>
          <div class="text-base text-right">
           <!-- Rating goes here -->
           <Rating :rating="rating" />
          </div>
        </div>
      </div>
    </article>
</template>

<style scoped>

</style>