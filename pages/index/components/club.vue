<template>
  <content-grid
    :leftStyle="[
      'xl:col-span-3',
      'sm:col-span-12',
      'text-center',
      'col-span-12',
    ]"
    :rightStyle="[
      'xl:col-span-3',
      'sm:col-span-4',
      'col-span-12',
      'cursor-pointer',
      'hover:-translate-y-2',
      'transition-transform',
    ]"
    :rightData="[
      '/img/首页顶部图片1.jpg',
      '/img/首页顶部图片2.jpg',
      '/img/首页顶部图片3.png',
    ]"
  >
    <template #left>
      <div class="h-full w-full flex flex-col justify-center">
        <h3 class="sm:text-5xl text-3xl">易享俱乐部</h3>
        <p class="text-lg font-thin text-gray-500 pt-8">
          开启您的易享之旅，易星越多、会员等级越高、好礼越丰富。
        </p>
        <p
          class="
            text-lg
            font-thin
            xl:pt-12
            sm:pt-3
            md:pt-3
            pt-2
            text-yellow-500
          "
        >
          <a href="#">了解更多 ›</a>
        </p>
      </div>
    </template>
    <template #right="scoped">
      <img :src="scoped.item" class="h-full w-full shadow-md" />
    </template>
  </content-grid>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import ContentGrid from "./content-grid.vue";

export default defineComponent({
  components: {
    ContentGrid,
  },
  setup() {
    return {};
  },
});
</script>

<style scoped>
</style>