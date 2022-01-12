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
    :rightData="data.tabs"
  >
    <template #left>
      <div class="flex flex-col justify-center w-full h-full">
        <h3 class="text-3xl sm:text-5xl">{{ data.title }}</h3>
        <p class="pt-8 text-lg font-thin text-gray-500">
          {{ data.info }}
        </p>
      </div>
    </template>
    <template #right="scoped">
      <!-- style="padding: 20px 30px; margin: 0 35px" -->
      <div
        class="px-0 py-10 pb-5 mx-0 text-center bg-white shadow-md  xl:px-2 xl:mx-8 md:mx-20 lg:mx-28 sm:mx-10 -top-8"
      >
        <div class="relative flex items-start justify-center -top-6">
          <img
            style="height: 100px"
            class="-mt-4"
            :src="encodeURI(scoped.item.img)"
            alt=""
          />
        </div>
        <h3 class="mb-3">{{ scoped.item.title }}</h3>
        <span>{{ scoped.item.info }}</span>
        <p class="pt-2 text-lg font-thin text-yellow-500">
          <a href="#">了解更多 ›</a>
        </p>
      </div>
    </template>
  </content-grid>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import ContentGrid from "./content-grid.vue";

export default defineComponent({
  props: {
    data: {
      type: Object,
      required: true,
    },
  },
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