<template>
  <div class="relative overflow-hidden bg-black">
    <img
      :src="data?.hero"
      class="hidden w-full sm:block"
      :style="imgStyle.large"
      alt=""
    />
    <img
      :src="data?.hero_small"
      class="block w-full sm:hidden"
      :style="imgStyle.small"
      alt=""
    />
    <div v-if="data.showBtn" class="absolute" style="left: 7%; bottom: 7%">
      <span class="ml-3">
        <button
          type="button"
          class="inline-flex items-center px-2 py-2 text-sm font-bold text-white bg-orange-500 rounded-md shadow-sm  lg:px-8 lg:py-3 md:px-5 md:py-2 sm:px-2 sm:py-2 hover:bg-orange-400 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-indigo-500"
        >
          <!-- Heroicon name: solid/link -->
          <svg
            class="w-5 h-5 mr-2 -ml-1 text-white"
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 20 20"
            fill="currentColor"
            aria-hidden="true"
          >
            <path
              fill-rule="evenodd"
              d="M12.586 4.586a2 2 0 112.828 2.828l-3 3a2 2 0 01-2.828 0 1 1 0 00-1.414 1.414 4 4 0 005.656 0l3-3a4 4 0 00-5.656-5.656l-1.5 1.5a1 1 0 101.414 1.414l1.5-1.5zm-5 5a2 2 0 012.828 0 1 1 0 101.414-1.414 4 4 0 00-5.656 0l-3 3a4 4 0 105.656 5.656l1.5-1.5a1 1 0 10-1.414-1.414l-1.5 1.5a2 2 0 11-2.828-2.828l3-3z"
              clip-rule="evenodd"
            />
          </svg>
          了解更多
        </button>
      </span>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  props: {
    data: {
      type: Object,
      required: true,
    },
    imgStyle: {
      type: Object,
      required: false,
      default: () => ({ large: [], small: [] }),
    },
  },
  setup() {
    return {};
  },
});
</script>

<style scoped>
</style>