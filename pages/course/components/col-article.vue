<template>
  <div>
    <div class="grid grid-cols-12 gap-8">
      <div class="md:col-start-2 md:col-span-5">
        <slot name="left" :item="data"> </slot>
      </div>
      <div class="md:col-start-7 xl:col-span-5 md:col-span-6">
        <slot name="right" :item="data"></slot>
      </div>
    </div>
    <hr class="mt-5 bg-gray-300" />
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