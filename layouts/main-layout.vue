<template>
  <div>
    <slot name="header">
      <header
        class="
          h-16
          bg-white
          block
          sm:flex
          md:flex
          w-full
          justify-around
          items-center
        "
      >
        <div class="hidden lg:hidden xl:block">
          <h2>
            <img class="xl:w-40 h-12" :src="data?.imgs.logo" alt="" />
          </h2>
        </div>
        <div>
          <ul class="h-16 font-bold flex items-center justify-around">
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
              class="
                inline-flex
                items-center
                px-6
                py-2
                border border-transparent
                rounded-md
                shadow-sm
                text-sm
                font-medium
                text-white
                bg-gray-800
                hover:bg-gray-700
                focus:outline-none
                focus:ring-2
                focus:ring-offset-2
                focus:ring-indigo-500
              "
            >
              登陆
            </button>
          </span>
        </div>
      </header>
    </slot>
    <slot name="hero" v-if="data">
      <div class="overflow-hidden bg-black relative">
        <img
          :src="data?.imgs.hero"
          class="hidden w-full sm:block"
          style=""
          alt=""
        />
        <img
          :src="data?.imgs.hero_small"
          class="block sm:hidden w-full"
          style=""
          alt=""
        />
        <div class="absolute" style="left: 7%; bottom: 7%">
          <span class="ml-3">
            <button
              type="button"
              class="
                inline-flex
                items-center
                lg:px-8 lg:py-3
                md:px-5 md:py-2
                sm:px-2 sm:py-2
                px-2
                py-2
                rounded-md
                shadow-sm
                text-sm
                font-bold
                text-white
                bg-orange-500
                hover:bg-orange-400
                focus:outline-none
                focus:ring-2
                focus:ring-offset-2
                focus:ring-indigo-500
              "
            >
              <!-- Heroicon name: solid/link -->
              <svg
                class="-ml-1 mr-2 h-5 w-5 text-white"
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 20 20"
                fill="currentColor"
                aria-hidden="true"
              >
                <path
                  fill-rule="evenodd"
                  d="M12.586 4.586a2 2 0 112.828 2.828l-3 3a2 2 0 01-2.828 0 1 1 0 00-1.414 1.414 4 4 0 005.656 0l3-3a4 4 0 00-5.656-5.656l-1.5 1.5a1 1 0 101.414 1.414l1.5-1.5zm-5 5a2 2 0 012.828 0 1 1 0 101.414-1.414 4 4 0 00-5.656 0l-3 3a4 4 0 105.656 5.656l1.5-1.5a1 1 0 10-1.414-1.414l-1.5 1.5a2 2 0 11-2.828-2.828l3-3z"
                  clip-rule="evenodd"
                />
              </svg>
              了解更多
            </button>
          </span>
        </div>
      </div>
    </slot>
    <slot name="content"><main>content</main></slot>

    <slot name="footer">
      <footer
        class="
          h-16
          sm:px-10
          bg-gray-800
          flex
          justify-between
          items-center
          text-gray-300
          font-light
        "
      >
        <div><NuxtLink to="/">易编程官网</NuxtLink></div>
        <div><a href="#">隐私政策</a><a href="#">条款和条件</a></div>
      </footer>
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