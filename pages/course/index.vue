<template>
  <div>
    <NuxtLayout name="main-layout">
      <template #content> I a course </template>
    </NuxtLayout>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  layout: false,
  setup() {
    return {};
  },
});
</script>

<style scoped>
</style>