<template>
  <div>
    <col-article
      :data="data"
      leftStyle="col-span-12 sm:col-span-6 pt-5 lg:col-span-8 xl:col-span-7"
      rightStyle="col-span-12 self-end text-center sm:col-span-6 lg:col-span-4 xl:col-span-5 "
      :showLine="false"
    >
      <template #left="scoped">
        <h4
          class="mt-20 text-base font-thin text-blue-400 lg:text-xl sm:text-lg"
        >
          {{ scoped.item.subtitle }}
        </h4>
        <h1
          class="mt-5 font-serif text-xl font-extrabold text-black  lg:text-3xl sm:text-2xl"
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