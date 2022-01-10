<template>
  <div>
    <NuxtLayout name="main-layout">
      <template #content>
        <Club />
        <Achievement class="overflow-hidden" />
        <Publish />
      </template>
    </NuxtLayout>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Club from "./components/club.vue";
import Achievement from "./components/achievement.vue";
import Publish from "./components/publish.vue";

export default defineComponent({
  components: { Club, Achievement, Publish },
  layout: false,
  setup() {
    return {};
  },
});
</script>

<style scoped>
</style>