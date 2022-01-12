<template>
  <div :class="gridStyle">
    <div :class="colStyle" v-for="(item, idx) in data" :key="item">
      <slot name="content" :item="item" :idx="idx"></slot>
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
      default: "col-span-12 shadow-md lg:col-span-3 sm:col-span-6",
    },
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