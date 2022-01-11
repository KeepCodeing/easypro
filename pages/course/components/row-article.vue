<template>
  <div>
    <div class="my-10 bg-white shadow-md" v-for="item in data" :key="item">
      <img :src="item.img" style="width: 100%" />
      <div class="p-8">
        <h2
          class="text-2xl font-bold text-center text-gray-600  sm:text-3xl md:text-4xl"
        >
          {{ item.title }}
        </h2>
        <h4
          class="mt-5 text-base font-thin text-left text-gray-400  sm:text-lg md:text-xl"
        >
          {{ item.info }}
        </h4>
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  props: {
    data: {
      type: Array,
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