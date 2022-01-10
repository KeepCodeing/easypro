<template>
  <div>
    <NuxtLayout name="main-layout">
      <template #content>
        <Club :data="data?.club" />
        <Achievement :data="data?.achievement" class="overflow-hidden" />
        <Publish :data="data?.publish" />
        <Swiper :data="data?.swiper" />
      </template>
    </NuxtLayout>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Club from "./components/club.vue";
import Achievement from "./components/achievement.vue";
import Publish from "./components/publish.vue";
import Swiper from "./components/swiper.vue";
import jdata from "@/data/index.json";

export default defineComponent({
  components: { Club, Achievement, Publish, Swiper },
  layout: false,
  setup() {
    const data = reactive(jdata);

    return {
      data,
    };
  },
});
</script>

<style scoped>
</style>