<template>
  <div class="my-10">
    <col-article
      :data="data"
      rightStyle="col-span-12 self-center sm:col-span-6 pt-5 lg:col-span-8 xl:col-span-7"
      leftStyle="col-span-12 self-end text-center sm:col-span-6 lg:col-span-4 xl:col-span-5 "
      :showLine="false"
    >
      <template #[whichSlot2]="scoped">
        <div class="text-center">
          <img :src="scoped.item.img" class="inline w-1/2 sm:w-full sm:block" />
        </div>
      </template>
      <template #[whichSlot1]="scoped">
        <h1
          class="mt-5 font-serif text-xl font-extrabold text-black  lg:text-3xl sm:text-2xl"
        >
          {{ scoped.item.title }}
        </h1>
        <h3 class="mt-2 text-lg font-thin text-gray-600 lg:text-2xl sm:text-xl">
          {{ scoped.item.info }}
        </h3>
      </template>
    </col-article>
    <card-list>
      <template #content>adfdaf</template>
    </card-list>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import { useMediaQuery, useEventListener, useDebounceFn } from "@vueuse/core";

export default defineComponent({
  props: {
    data: {
      type: Object,
      required: true,
    },
  },
  setup() {
    const isMobileScreen = ref<any>(false);
    const whichSlot1 = ref("left");
    const whichSlot2 = ref("right");
    const cmpSlot = () => {
      whichSlot1.value = isMobileScreen.value ? "left" : "right";
      whichSlot2.value = isMobileScreen.value ? "right" : "left";
    };
    isMobileScreen.value = useMediaQuery("(max-width: 640px)").value;
    cmpSlot();
    if (process.client) {
      useEventListener(
        window,
        "resize",
        useDebounceFn(() => {
          isMobileScreen.value = useMediaQuery("(max-width: 640px)").value;
          cmpSlot();
        }, 50)
      );
    }
    return {
      whichSlot1,
      whichSlot2,
    };
  },
});
</script>

<style scoped>
</style>