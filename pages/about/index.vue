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
      <template #content> </template>
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