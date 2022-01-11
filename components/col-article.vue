<template>
  <div>
    <div :class="gridStyle?.split(' ')">
      <div :class="leftStyle?.split(' ')">
        <slot name="left" :item="data"> </slot>
      </div>
      <div :class="rightStyle?.split(' ')">
        <slot name="right" :item="data"></slot>
      </div>
    </div>
    <hr v-if="showLine" class="mt-5 bg-gray-300" />
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
      type: String,
      required: false,
      default: "grid grid-cols-12 gap-8",
    },
    leftStyle: {
      type: String,
      required: false,
      default: "xl:col-start-2 xl:col-span-5 col-span-6 col-start-1",
    },
    rightStyle: {
      type: String,
      required: false,
      default: "md:col-start-7 xl:col-span-5 md:col-span-6",
    },
    showLine: {
      type: Boolean,
      required: false,
      default: true,
    },
  },
  setup() {
    return {};
  },
});
</script>

<style scoped>
</style>