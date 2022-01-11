<template>
  <div class="pb-16 sm:pb-0">
    <slot name="header">
      <template class="hidden sm:block">
        <header
          class="items-center justify-around block w-full h-16 bg-white  sm:flex md:flex"
        >
          <div class="hidden lg:hidden xl:block">
            <h2>
              <img class="h-12 xl:w-40" :src="data?.imgs.logo" alt="" />
            </h2>
          </div>
          <div>
            <ul class="flex items-center justify-around h-16 font-bold">
              <li
                class="sm:mx-3 md:mx-3 lg:mx-6 sm:block"
                :class="{ hidden: item.hidden }"
                v-for="(item, idx) in data?.tabs"
                :key="idx"
              >
                <NuxtLink :to="item.link">{{ item.title }}</NuxtLink>
              </li>
            </ul>
          </div>
          <div class="hidden sm:hidden md:block">
            <span class="sm:ml-3">
              <button
                type="button"
                class="inline-flex items-center px-6 py-2 text-sm font-medium text-white bg-gray-800 border border-transparent rounded-md shadow-sm  hover:bg-gray-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500"
              >
                登陆
              </button>
            </span>
          </div>
        </header>
      </template>
    </slot>
    <slot name="hero"> </slot>
    <slot name="content"><main>content</main></slot>

    <slot name="footer">
      <footer
        class="flex items-center justify-between h-16 font-light text-gray-300 bg-gray-800  sm:px-10"
      >
        <div><NuxtLink to="/">易编程官网</NuxtLink></div>
        <div><a href="#">隐私政策</a><a href="#">条款和条件</a></div>
      </footer>
    </slot>

    <slot name="tabbar">
      <div
        class="fixed bottom-0 flex items-center justify-between block w-full h-16 bg-white  sm:hidden px-14 bg-gray-50"
      >
        <template v-for="item in data.tabs" :key="item">
          <div class="text-center" v-if="item.tab">
            <NuxtLink :to="item.link">
              <div>{{ item.title }}</div>
              <div class="flex items-center justify-center">
                <svg
                  t="1641821937029"
                  class="icon"
                  viewBox="0 0 1024 1024"
                  version="1.1"
                  xmlns="http://www.w3.org/2000/svg"
                  p-id="2191"
                  width="30"
                  height="30"
                >
                  <path
                    fill="currentColor"
                    class="text-gray-700"
                    d="M969.6 502.4l-118.4-112-323.2-300.8c-9.6-9.6-22.4-9.6-32 0l-313.6 297.6c-3.2 3.2-6.4 6.4-9.6 9.6l-118.4 112c-9.6 9.6-9.6 22.4 0 32s22.4 9.6 32 0l83.2-80 0 393.6c0 48 41.6 89.6 92.8 89.6l83.2 0c38.4 0 70.4-28.8 70.4-67.2l0-217.6 99.2 0 99.2 0 0 217.6c0 35.2 32 67.2 70.4 67.2l83.2 0c51.2 0 92.8-38.4 92.8-89.6l0-396.8 80 73.6c9.6 9.6 22.4 9.6 32 0C979.2 524.8 979.2 512 969.6 502.4zM809.6 857.6c0 25.6-19.2 44.8-44.8 44.8l-83.2 0c-12.8 0-22.4-9.6-22.4-22.4L659.2 640c0-12.8-9.6-22.4-22.4-22.4l-121.6 0-121.6 0c-12.8 0-22.4 9.6-22.4 22.4l0 240c0 12.8-9.6 22.4-22.4 22.4l-83.2 0c-25.6 0-44.8-19.2-44.8-44.8l0-438.4 294.4-281.6 294.4 281.6L809.6 857.6z"
                    p-id="2192"
                  ></path>
                </svg>
              </div>
            </NuxtLink>
          </div>
        </template>
      </div>
    </slot>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import jdata from "@/data/main-layout.json";

export default defineComponent({
  setup() {
    let data: any = reactive(jdata);

    return {
      data,
    };
  },
});
</script>

<style scoped>
footer a {
  @apply mx-2;
}
footer a:hover {
  @apply text-gray-200;
}
</style>