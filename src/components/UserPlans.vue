<template>
  <div
    class="absolute w-full h-auto flex flex-col items-center justify-center z-10 gap-y-10 bg-gray-100 py-10"
  >
    <h1 class="text-3xl font-bold">Our Pricing</h1>
    <div class="flex gap-x-4">
      <p :class="`text-xl ${isOn ? 'text-blue-900/80' : ''}`">Annually</p>
      <button
        @click="isOn = !isOn"
        :class="`flex rounded-full w-[64px] p-1 ${
          isOn ? 'bg-blue-900' : 'bg-blue-400'
        }`"
      >
        <div
          :class="`bg-white rounded-full w-7 h-7 ${
            isOn ? '' : 'transform translate-x-full'
          }`"
        ></div>
      </button>
      <p :class="`text-xl ${isOn ? '' : 'text-blue-900/80'}`">Monthly</p>
    </div>

    <div class="grid md:grid-cols-3 gap-y-10">
      <!-- the left side  -->
      <div
        class="w-[400px] bg-white flex flex-col items-center justify-center rounded-md gap-y-8 px-5 py-20 text-gray-800 my-8 shadow-lg"
      >
        <p class="text-">Professional</p>
        <h1 class="text-4xl items-center justify-center flex gap-3">
            <template v-if="isOn">
            $<span class="text-7xl font-bold">{{
              planPrices[0].annually
            }}</span>
          </template>
          <template v-else>
            $<span class="text-7xl font-bold">{{ planPrices[0].monthly }}</span>
          </template>
        </h1>
        <div class="w-full text-center space-y-5">
          <div class="w-full h-[1px] bg-gray-300"></div>
          <p class="text-md">1 TB Storage</p>
          <div class="w-full h-[1px] bg-gray-300"></div>
          <p class="text-md">5 Users Allowed</p>
          <div class="w-full h-[1px] bg-gray-300"></div>
          <p class="text-md">Send up to 10 GB</p>
          <div class="w-full h-[1px] bg-gray-300"></div>
        </div>
        <button
          class="bg-blue-900/80 text-md w-full p-5 rounded-md mt-2 text-white"
        >
          LEARN MORE
        </button>
      </div>

      <!-- the middle  -->
      <div
        class="w-[400px] bg-blue-900/80 flex flex-col items-center justify-center rounded-md gap-y-8 px-5 py-20 text-white shadow-lg"
      >
        <p class="text-">Professional</p>
        <h1 class="text-4xl items-center justify-center flex gap-3">
          <template v-if="isOn">
            $<span class="text-7xl font-bold">{{
              planPrices[1].annually
            }}</span>
          </template>
          <template v-else>
            $<span class="text-7xl font-bold">{{ planPrices[1].monthly }}</span>
          </template>
        </h1>
        <div class="w-full text-center space-y-5">
          <div class="w-full h-[1px] bg-gray-100"></div>
          <p class="text-md">1 TB Storage</p>
          <div class="w-full h-[1px] bg-gray-100"></div>
          <p class="text-md">5 Users Allowed</p>
          <div class="w-full h-[1px] bg-gray-100"></div>
          <p class="text-md">Send up to 10 GB</p>
          <div class="w-full h-[1px] bg-gray-100"></div>
        </div>
        <button
          class="bg-white text-indigo-700 text-md w-full p-5 rounded-md mt-2"
        >
          LEARN MORE
        </button>
      </div>

      <!-- the right side  -->
      <div
        class="w-[400px] bg-white flex flex-col items-center justify-center rounded-md gap-y-8 px-5 py-20 text-gray-800 my-8 shadow-lg"
      >
        <p class="text-">Professional</p>
        <h1 class="text-4xl items-center justify-center flex gap-3">
            <template v-if="isOn">
            $<span class="text-7xl font-bold">{{
              planPrices[2].annually
            }}</span>
          </template>
          <template v-else>
            $<span class="text-7xl font-bold">{{ planPrices[2].monthly }}</span>
          </template>
        </h1>
        <div class="w-full text-center space-y-5">
          <div class="w-full h-[1px] bg-gray-300"></div>
          <p class="text-md">1 TB Storage</p>
          <div class="w-full h-[1px] bg-gray-300"></div>
          <p class="text-md">5 Users Allowed</p>
          <div class="w-full h-[1px] bg-gray-300"></div>
          <p class="text-md">Send up to 10 GB</p>
          <div class="w-full h-[1px] bg-gray-300"></div>
        </div>
        <button
          class="bg-blue-900/80 text-white text-md w-full p-5 rounded-md mt-2"
        >
          LEARN MORE
        </button>
      </div>
    </div>
  </div>
  <!-- <div class="relative flex w-full h-full justify-between">
    <img src="@/assets/bg-bottom.svg" alt="bg image" class="bottom-0" />
    <img src="@/assets/bg-top.svg" alt="bg image" class="" />
  </div> -->
</template>

<script setup>
import { ref } from "vue";

const isOn = ref(false);

const planPrices = [
  { id: 1, annually: 199.99, monthly: 19.99 },
  { id: 2, annually: 249.99, monthly: 24.99 },
  { id: 3, annually: 399.99, monthly: 39.99 },
];
</script>
