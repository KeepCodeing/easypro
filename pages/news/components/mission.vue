<template>
  <div>
    <col-article
      :data="data"
      leftStyle="col-span-12 sm:col-span-6 pt-5 lg:col-span-8 xl:col-span-7"
      rightStyle="col-span-12 self-center text-center sm:col-span-6 lg:col-span-4 xl:col-span-5 "
      gridStyle="grid grid-cols-12 gap-8 py-5"
      :showLine="false"
    >
      <template #left="scoped">
        <h1
          class="mt-5 font-serif text-xl font-extrabold text-yellow-400  lg:text-4xl sm:text-2xl"
        >
          {{ scoped.item.title }}
        </h1>
        <h3 class="mt-2 text-lg font-thin text-gray-600 lg:text-2xl sm:text-xl">
          {{ scoped.item.info }}
        </h3>
      </template>
      <template #right="scoped">
        <img :src="scoped.item.img" class="inline w-1/2 sm:w-full sm:block" />
      </template>
    </col-article>
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