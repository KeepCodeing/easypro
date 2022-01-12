<template>
  <div class="py-10 bg-gray-100 sm:px-20">
    <div
      class="flex items-center justify-between px-0 pb-5 overflow-x-scroll overflow-y-hidden "
    >
      <div
        style="width: 288px"
        class="relative mx-10 font-medium text-gray-400 bg-white rounded-md shadow-md  shrink-0"
        v-for="item in data.data"
        :key="item"
      >
        <img :src="item.img" class="w-full" style="height: 168px" />
        <span class="inline-block p-3">{{ item.title }}</span>
        <span
          class="absolute left-0 inline-block px-5 py-2 text-white bg-yellow-500  top-5"
          >{{ item.tag }}</span
        >
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