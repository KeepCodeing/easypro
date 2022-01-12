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
    :rightData="data.imgs"
  >
    <template #left>
      <div class="flex flex-col justify-center w-full h-full">
        <h3 class="text-3xl sm:text-5xl">{{ data.title }}</h3>
        <p class="pt-8 text-lg font-thin text-gray-500">
          {{ data.info }}
        </p>
        <p
          class="pt-2 text-lg font-thin text-yellow-500  xl:pt-12 sm:pt-3 md:pt-3"
        >
          <a href="#">了解更多 ›</a>
        </p>
      </div>
    </template>
    <template #right="scoped">
      <img :src="encodeURI(scoped.item)" class="w-full h-full shadow-md" />
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