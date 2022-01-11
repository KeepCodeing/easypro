<template>
  <div>
    <NuxtLayout name="main-layout">
      <template #hero>
        <Hero
          :data="{
            hero: 'img/首页顶部图片2.jpg',
            hero_small: 'img/首页顶部图片2.jpg',
            showBtn: false,
          }"
          :imgStyle="{
            large: [
              'aspect-ratio: 16 / 9',
              'max-height: 100vh',
              'filter: blur(15px)',
              'transform: scale(1.1)',
            ],
            small: [
              'aspect-ratio: 4 / 3',
              'max-height: 100vh',
              'filter: blur(15px)',
              'transform: scale(1.1)',
            ],
          }"
        >
          <template #extern>
            <div class="absolute w-full px-5 text-center text-white bottom-11">
              <p class="text-base font-medium md:text-xl">编程知识</p>
              <h2 class="mt-3 text-4xl font-bold md:text-7xl">
                编程的起源与发展
              </h2>
              <h3 class="mt-3 text-xl font-thin md:text-3xl title">
                在第二次世界大战中,美国政府寻求计算机以开发潜在的战略价值。这促进了计算机的研究与发展。
              </h3>
            </div>
          </template>
        </Hero>
      </template>
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
.title {
  font-family: "ACaslonPro", Georgia, Times, "Times New Roman", serif;
}
</style>