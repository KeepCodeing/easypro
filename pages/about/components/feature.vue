<template>
  <div style="background-color: rgb(247, 246, 249)" class="p-10 my-10">
    <div class="grid grid-cols-12 gap-8">
      <div class="col-span-12 mb-2 text-center sm:mb-5">
        <span
          class="inline px-10 py-4 text-3xl font-bold text-black sm:text-4xl"
          >{{ data.title }}</span
        >
      </div>
      <div
        class="col-span-12 text-center sm:col-span-4"
        v-for="item in data.tabs"
        :key="item"
      >
        <div>
          <img
            :src="item.img"
            class="inline border-4 border-yellow-400 rounded-full  h-36 sm:h-auto sm:mt-7"
          />
        </div>
        <h3
          class="mt-4 overflow-hidden text-base font-thin text-gray-500  md:text-2xl text-ellipsis whitespace-nowrap sm:text-xl"
        >
          {{ item.title }}
        </h3>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  props: {
    data: {
      type: Object,
      required: true,
    },
  },
  setup() {
    return {};
  },
});
</script>

<style scoped>
</style>