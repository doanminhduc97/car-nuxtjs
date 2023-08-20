<template>
  <!-- Home hero -->
  <div class="relative h-screen w-100 bg-no-repeat bg-cover bg-bottom bg-[url('https://cdn.ferrari.com/cms/network/media/img/resize/646a3f2579608a0023b0c63d-ferrari_296_gt3_nurburgring_2023_news_land')]">
    
    <div class="z-10 absolute w-full flex justify-center items-center">
      <div class="text-center w-1/2">
        <h1 class="text-8xl font-serif mb-10 text-white">Find your drive</h1>
        <!-- Home search bar-->
          <!-- <div class="font-serif w-[1000px] text-2xl rounded-full bg-white flex justify-between overflow-hidden drop-shadow-2xl mx-auto">
            <input type="text" class="py-3 px-5 w-full text-2xl rounded-full focus:outline-none"
            placeholder="Search by city...">
            <button class="bg-sky-500 px-10 text-white">Search</button>
          </div> -->
          <SearchBar />
        <!-- Home search -->
      </div>
    </div>
    <div class="z-1 absolute w-full h-full bg-black opacity-50"></div>
  </div>
  <!-- Home hero -->
</template>

<script setup>
import SearchBar from "./SearchBar.vue"
</script>