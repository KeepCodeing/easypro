<template>
  <content-grid
    :leftStyle="['text-center', 'col-span-12', 'row-span-2', 'md:col-span-6']"
    :rightStyle="['md:col-span-3', 'col-span-12', 'row-span-1']"
    :gridStyle="[
      'grid',
      'gap-4',
      'grid-rows-2',
      'grid-cols-12',
      'py-16',
      'px-6',
    ]"
    :rightData="[
      { title: '40+', info: 'Happy Clients' },
      { title: '540+', info: 'Projects Compoleted' },
      { title: '300', info: 'Dedicated Members' },
      { title: '25+', info: 'Awards Won' },
    ]"
    gridColor="bg-gray-100"
  >
    <template #left>
      <div class="h-full w-full font-semibold flex flex-col justify-center">
        <h3 class="sm:text-5xl text-2xl">
          Our <span class="text-yellow-400">18 Years</span>
          <p class="py-2"></p>
          Of Achievements
        </h3>
      </div>
    </template>
    <template #right="scoped">
      <div class="info">
        <h3 class="font-bold text-3xl">{{ scoped.item.title }}</h3>
        <span class="font-medium text-lg text-gray-500">{{
          scoped.item.info
        }}</span>
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
.info {
  position: relative;
}
.info::before {
  content: " ";
  border: 2px solid rgb(202 138 4);
  background: rgb(202 138 4);
  position: absolute;
  height: 60px;
  left: -20px;
}
/* :rightData="[
      { title: '短视频平台', info: '易享卡新升级更多心意好礼' },
      { title: '短视频平台', info: '易享卡新升级更多心意好礼' },
      { title: '短视频平台', info: '易享卡新升级更多心意好礼' },
      { title: '短视频平台', info: '易享卡新升级更多心意好礼' },
    ]" */
</style>