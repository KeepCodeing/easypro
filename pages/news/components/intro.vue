<template>
  <div>
    <card-list colStyle="md:col-span-4 col-span-12 mt-20" :data="data">
      <template #content="scoped">
        <div
          class="h-full p-10 bg-white rounded-lg sm:p-5"
          :style="{ backgroundColor: colorArr[scoped.idx % 3] }"
        >
          <div class="text-center md:mb-5 icon" style="margin-top: -35%">
            <img
              class="inline w-2/5 md:w-1/2 sm:w-1/3 aspect-square"
              :src="scoped.item.img"
            />
          </div>
          <div
            class="text-xl font-black text-center text-black  lg:text-4xl md:text-3xl sm:text-2xl"
          >
            {{ scoped.item.title }}
          </div>
          <div
            class="mt-10 font-serif text-base font-bold text-gray-400  lg:text-2xl md:text-xl sm:text-lg"
          >
            {{ scoped.item.info }}
          </div>
        </div>
      </template>
    </card-list>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  props: {
    data: {
      type: Array,
      required: true,
    },
  },
  setup() {
    const colorArr = [
      "rgb(243,241,247)",
      "rgb(232,230,246)",
      "rgb(238,229,233)",
    ];
    return {
      colorArr,
    };
  },
});
</script>

<style scoped>
@media (max-width: 768px) {
  .icon {
    margin-top: -20% !important;
  }
}
@media (max-width: 640px) {
  .icon {
    margin-top: -30% !important;
  }
}
</style>