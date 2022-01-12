<template>
  <div>
    <NuxtLayout name="main-layout">
      <template #hero>
        <Hero
          :data="data.hero"
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
              <p class="text-base font-medium md:text-xl">
                {{ data.hero.headtitle }}
              </p>
              <h2 class="mt-3 text-4xl font-bold md:text-7xl">
                {{ data.hero.title }}
              </h2>
              <h3 class="mt-3 text-xl font-thin md:text-3xl title">
                {{ data.hero.subtitle }}
              </h3>
            </div>
          </template>
        </Hero>
      </template>
      <template #content
        ><div
          class="flex flex-col items-center justify-center px-10 bg-white  xl:px-40"
        >
          <h3 class="mt-5 text-base tab-title">
            <a href="#" v-for="item in data.article.tab" :key="item">{{
              item
            }}</a>
          </h3>
          <hr class="w-full mt-5 bg-gray-300" />
          <!--  这里写来写去还是只能写成组件循环的形式，因为下面要判断用哪个插槽，所以
                循环里的值必须是插槽能用到的..写组件里就只能作为scoped变量取出来，但
                用不了 -->
          <col-article
            v-for="(item, idx) in data.article.list"
            :key="item"
            :data="item"
            class="hidden mx-auto my-5 lg:block"
          >
            <!-- 通过切换插槽完成切换位置的效果 -->
            <template v-slot:[whichSlot1(idx)]="scoped"
              ><h2 class="pt-5 text-4xl font-medium text-gray-600">
                {{ scoped.item.title }}
              </h2>
              <p class="mt-5 text-xl font-medium text-gray-400">
                {{ scoped.item.info }}
              </p></template
            >
            <template v-slot:[whichSlot2(idx)]="scoped"
              ><img
                :src="scoped.item.img"
                class="w-full md:aspect-square xl:aspect-auto"
              />
            </template>
          </col-article>
          <row-article :data="data.article.list" class="block lg:hidden">
          </row-article>
        </div>
      </template>
    </NuxtLayout>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import colArticle from "../../components/col-article.vue";
import jdata from "@/data/course.json";

export default defineComponent({
  components: { colArticle },
  layout: false,
  setup() {
    const whichSlot1 = (item) => (item % 2 === 0 ? "right" : "left");
    const whichSlot2 = (item) => (item % 2 !== 0 ? "right" : "left");
    const data = reactive(jdata);
    return {
      whichSlot1,
      whichSlot2,
      data,
    };
  },
});
</script>

<style scoped>
.title {
  font-family: "ACaslonPro", Georgia, Times, "Times New Roman", serif;
}
.tab-title {
  text-align: center;
}
.tab-title a {
  margin: 0 5px;
}
.tab-title a:hover {
  color: orange;
}
.tab-title a:first-child {
  color: orange;
}
.tab-title a::after {
  content: " ";
  border-right: 1px solid gray;
  height: 5px;
  padding: 0 3px;
}
.tab-title a:last-of-type::after {
  border: none;
}
@media (min-width: 1024px) and (max-width: 1280px) {
  .my-aspect-square {
    aspect-ratio: 1 / 1 !important;
  }
}
</style>