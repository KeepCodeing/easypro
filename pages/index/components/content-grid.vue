<template>
  <div :class="[...gridStyle, gridColor]">
    <div :class="leftStyle">
      <slot name="left"></slot>
    </div>
    <div :class="rightStyle" v-for="item in rightData" :key="item">
      <slot name="right" :item="item"></slot>
    </div>
  </div>
</template>

<script lang="ts">
// 迫真栅格布局组件，实际上好像没有封装的必要，不过确实大部分代码有重复
// 这个组件提供两块区域，是针对index页面而言的，左边区域固定为标题，
// 右边区域可以传入一个数组，渲染若干个元素
import { defineComponent } from "vue";

export default defineComponent({
  props: {
    leftStyle: {
      type: Array,
      required: false,
      default: () => [],
    },
    rightStyle: {
      type: Array,
      required: false,
      default: () => [],
    },
    rightData: {
      type: Array,
      required: false,
      default: () => [],
    },
    gridStyle: {
      type: Array,
      required: false,
      default: () => ["grid", "gap-4", "grid-cols-12", "py-8", "px-6"],
    },
    gridColor: {
      type: String,
      required: false,
      default: () => "white",
    },
  },
  setup() {
    return {};
  },
});
</script>

<style scoped>
</style>