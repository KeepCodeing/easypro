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
              <template v-for="(item, idx) in data?.tabs" :key="idx">
                <li
                  class="sm:mx-3 md:mx-3 lg:mx-6 sm:block"
                  :class="{
                    hidden: item.hidden,
                    'text-yellow-400': $route.path === item.link,
                  }"
                >
                  <NuxtLink :to="item.hidden ? '/' : item.link">{{
                    item.title
                  }}</NuxtLink>
                </li>
              </template>
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
        style="bottom: -2px"
        class="fixed flex items-center justify-between block w-full h-16 bg-white  sm:hidden px-14 bg-gray-50"
      >
        <template v-for="item in data.tabs" :key="item">
          <div class="text-center" v-if="item.tab">
            <NuxtLink :to="item.link">
              <div
                class="font-bold"
                :class="{ 'text-yellow-400': $route.path === item.link }"
              >
                {{ item.title }}
              </div>
              <div class="text-center">
                <span
                  class="mt-2"
                  style="font-size: 20px"
                  :class="[
                    item.icon,
                    { 'text-yellow-400': $route.path === item.link },
                  ]"
                ></span>
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