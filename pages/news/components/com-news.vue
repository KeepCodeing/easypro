<template>
  <div>
    <card-list :data="data" colStyle="col-span-12 lg:col-span-4">
      <template #content="scoped"
        ><div class="relative h-full bg-white shadow-md">
          <div
            class="w-full bg-center bg-no-repeat bg-cover lg:h-72 md:h-64 h-60"
            :style="{ backgroundImage: `url(${scoped.item.img})` }"
          ></div>
          <div
            class="px-5 mt-8 overflow-hidden text-2xl font-bold text-center text-gray-600  text-ellipsis whitespace-nowrap sm:text-3xl"
          >
            {{ scoped.item.title }}
          </div>
          <div
            class="px-5 pt-5 pb-16 text-base font-thin text-left text-gray-400  sm:text-base md:text-xl"
          >
            {{ scoped.item.info }}
          </div>
          <p class="absolute bottom-5 left-5">
            <a href="#" class="text-left text-blue-400 hover:text-blue-500"
              >了解更多<svg
                class="inline w-4 h-4 ml-2"
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 20 20"
                fill="currentColor"
                aria-hidden="true"
              >
                <path
                  fill-rule="evenodd"
                  d="M12.586 4.586a2 2 0 112.828 2.828l-3 3a2 2 0 01-2.828 0 1 1 0 00-1.414 1.414 4 4 0 005.656 0l3-3a4 4 0 00-5.656-5.656l-1.5 1.5a1 1 0 101.414 1.414l1.5-1.5zm-5 5a2 2 0 012.828 0 1 1 0 101.414-1.414 4 4 0 00-5.656 0l-3 3a4 4 0 105.656 5.656l1.5-1.5a1 1 0 10-1.414-1.414l-1.5 1.5a2 2 0 11-2.828-2.828l3-3z"
                  clip-rule="evenodd"
                /></svg
            ></a>
          </p>
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
    return {};
  },
});
</script>

<style scoped>
</style>