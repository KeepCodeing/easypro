<template>
  <content-grid
    :leftStyle="[
      'xl:col-span-3',
      'sm:col-span-12',
      'text-center',
      'col-span-12',
    ]"
    :rightStyle="[
      'xl:col-span-2',
      'sm:col-span-6',
      'col-span-6',
      'cursor-pointer',
      'hover:-translate-y-2',
      'transition-transform',
    ]"
    :rightData="[
      { title: '短视频平台', info: '易享卡新升级更多心意好礼' },
      { title: '线上精品教学', info: '易享卡新升级更多心意好礼' },
      { title: '线下课程优选', info: '易享卡新升级更多心意好礼' },
      { title: '优秀教师解答', info: '易享卡新升级更多心意好礼' },
    ]"
  >
    <template #left>
      <div class="h-full w-full flex flex-col justify-center">
        <h3 class="sm:text-5xl text-3xl">易编程优选</h3>
        <p class="text-lg font-thin text-gray-500 pt-8">
          在各大平台上为中国教育贡献力量
        </p>
      </div>
    </template>
    <template #right="scoped">
      <!-- style="padding: 20px 30px; margin: 0 35px" -->
      <div
        class="
          text-center
          bg-white
          shadow-md
          xl:px-2 xl:mx-8
          md:mx-20
          lg:mx-28
          sm:mx-10
          px-0
          mx-0
          -top-8
          py-10
          pb-5
        "
      >
        <div class="flex justify-center items-start relative -top-6">
          <img
            style="height: 100px"
            class="-mt-4"
            src="/img/card1.png"
            alt=""
          />
        </div>
        <h3 class="mb-3">{{ scoped.item.title }}</h3>
        <span>{{ scoped.item.info }}</span>
      </div>
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