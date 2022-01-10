<template>
  <div class="bg-gray-100 sm:px-20 py-10">
    <div
      class="
        flex
        px-0
        justify-between
        items-center
        overflow-x-scroll overflow-y-hidden
        pb-5
      "
    >
      <div
        style="width: 288px"
        class="
          bg-white
          rounded-md
          mx-10
          shrink-0
          text-gray-400
          font-medium
          shadow-md
          relative
        "
        v-for="item in data.data"
        :key="item"
      >
        <img :src="item.img" class="w-full" style="height: 168px" />
        <span class="p-3 inline-block">{{ item.title }}</span>
        <span
          class="
            inline-block
            absolute
            bg-yellow-500
            text-white
            left-0
            top-5
            px-5
            py-2
          "
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