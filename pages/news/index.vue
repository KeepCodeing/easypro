<template>
  <div>
    <NuxtLayout name="main-layout">
      <template #hero>
        <div class="relative flex items-center justify-center py-24">
          <div class="text-center text-white">
            <h1 class="text-4xl font-black">易编程在中国</h1>
            <h4 class="px-5 mt-5 text-xl font-medium">
              我们希望将编程教育带入中小学当中，让更多的孩子有机会接触、了解到编程。
            </h4>
          </div>
          <div
            style="background-image: url('img/关于-中图2.png')"
            class="absolute w-full h-full bg-center bg-cover -z-10 hero"
          ></div>
        </div>
      </template>
      <template #content>
        <div class="px-10 my-10 lg:my-20 lg:px-20 xl:px-40">
          <Intro :data="data.intro"></Intro>
        </div>
        <div
          class="px-10 lg:px-20 xl:px-40"
          style="background-color: rgb(247, 246, 249)"
        >
          <Mission :data="data.mission"></Mission>
        </div>
        <div class="px-10 my-10 lg:my-20 lg:px-20">
          <News :data="data.news"></News>
        </div>
      </template>
    </NuxtLayout>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import jdata from "@/data/news.json";
import Intro from "./components/intro.vue";
import Mission from "./components/mission.vue";
import News from "./components/news.vue";

export default defineComponent({
  components: { Intro, Mission, News },
  setup() {
    const data = reactive(jdata);
    return {
      data,
    };
  },
});
</script>

<style scoped>
.hero::after {
  background-image: linear-gradient(
    -180deg,
    rgba(0, 0, 0, 0.35) 0%,
    rgba(0, 0, 0, 0.7) 81%
  );
  content: "";
  height: 100%;
  position: absolute;
  width: 100%;
  left: 0;
  bottom: 0;
}
</style>