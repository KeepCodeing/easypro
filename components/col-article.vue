<template>
  <div>
    <div :class="gridStyle?.grid.split(' ')">
      <div :class="gridStyle?.left.split(' ')">
        <slot name="left" :item="data"> </slot>
      </div>
      <div :class="gridStyle?.right.split(' ')">
        <slot name="right" :item="data"></slot>
      </div>
    </div>
    <hr v-if="gridStyle?.showLine" class="mt-5 bg-gray-300" />
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
    gridStyle: {
      type: Object,
      required: false,
      default: () => ({
        grid: "grid grid-cols-12 gap-8",
        left: "xl:col-start-2 xl:col-span-5 col-span-6 col-start-1",
        right: "md:col-start-7 xl:col-span-5 md:col-span-6",
        showLine: true,
      }),
    },
  },
  setup() {
    return {};
  },
});
</script>

<style scoped>
</style>