<template>
  <div>
    <NuxtLayout name="main-layout">
      <template #hero
        ><div
          class="text-center py-36"
          style="background-color: rgb(247, 246, 249)"
        >
          <h1 class="text-4xl font-black text-black">
            <span class="text-yellow-500">易编程教育™</span>
            <p class="mt-4"></p>
            为中国学生送去优质的教育
          </h1>
          <h3 class="mt-10 font-serif text-2xl font-bold text-gray-400">
            了解我们的团队，公司，以及获取更多相关资讯！
          </h3>
        </div>
      </template>
      <template #content>
        <div class="px-5 md:px-20 xl:px-40">
          <Mission :data="data.mission" />
        </div>
        <div class="px-5">
          <Feature :data="data.featute" />
        </div>
        <div class="px-5 md:px-20 lg:px-30">
          <Intro :data="data.intro" />
        </div>
      </template>
    </NuxtLayout>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import jdata from "@/data/about.json";
import Mission from "./components/mission.vue";
import Feature from "./components/feature.vue";
import Intro from "./components/intro.vue";

export default defineComponent({
  layout: false,
  components: {
    Mission,
    Feature,
    Intro,
  },
  setup() {
    const data = reactive(jdata);
    return { data };
  },
});
</script>

<style scoped>
</style>