<template>
  <content-grid
    :leftStyle="['text-center', 'col-span-12', 'row-span-2', 'md:col-span-6']"
    :rightStyle="['md:col-span-3', 'col-span-6', 'row-span-1']"
    :gridStyle="[
      'grid',
      'gap-8',
      'grid-rows-2',
      'grid-cols-12',
      'lg:py-16',
      'py-14',
      'px-6',
    ]"
    :rightData="data.info"
    gridColor="bg-gray-100"
  >
    <template #left>
      <div class="h-full w-full font-semibold flex flex-col justify-center">
        <h3 class="sm:text-5xl text-4xl">
          {{ data.up_title }}
          <span class="text-yellow-400">{{ data.mid_title }}</span>
          <p class="py-2"></p>
          {{ data.down_title }}
        </h3>
      </div>
    </template>
    <template #right="scoped">
      <div class="info">
        <h3 class="font-bold text-3xl">{{ scoped.item.title }}</h3>
      </div>
      <span
        class="
          font-medium
          pl-5
          whitespace-nowrap
          break-all
          text-lg text-center text-gray-500
        "
        >{{ scoped.item.subtitle }}</span
      >
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
.info {
  position: relative;
  display: flex;
  justify-content: flex-start;
  align-items: center;
}
.info::before {
  content: " ";
  border: 2px solid rgb(202 138 4);
  background: rgb(202 138 4);
  height: 60px;
  margin-right: 20px;
}
</style>