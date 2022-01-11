<template>
  <div :class="gridStyle">
    <div :class="colStyle">
      <slot name="content"></slot>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  props: {
    gridStyle: {
      type: String,
      required: false,
      default: "grid grid-cols-12 gap-8 bg-white",
    },
    colStyle: {
      type: String,
      required: false,
      default: "col-span-12 shadow-md md:col-span-3 sm:col-span-6",
    },
  },
  setup() {
    return {};
  },
});
</script>

<style scoped>
</style>