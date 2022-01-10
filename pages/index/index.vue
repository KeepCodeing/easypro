<template>
  <div>
    <NuxtLayout name="main-layout">
      <template #content>
        <Club />
        <Achievement />
      </template>
    </NuxtLayout>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Club from "./components/club.vue";
import Achievement from "./components/achievement.vue";

export default defineComponent({
  components: { Club, Achievement },
  layout: false,
  setup() {
    return {};
  },
});
</script>

<style scoped>
</style>