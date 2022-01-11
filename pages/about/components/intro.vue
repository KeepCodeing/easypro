<template>
  <div class="my-10">
    <col-article
      :data="data.core"
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
    <card-list
      :data="data.com_intro"
      colStyle="col-span-12 rounded-2xl shadow-md xl:col-span-3 sm:col-span-6 bg-white py-8 px-10"
      style="background-color: rgb(247, 246, 249)"
      class="p-5 my-10 lg:p-10 rounded-2xl"
    >
      <template #content="scoped">
        <div class="content">
          <h1 class="stick">
            <svg
              t="1641914116851"
              class="icon"
              viewBox="0 0 1024 1024"
              version="1.1"
              xmlns="http://www.w3.org/2000/svg"
              p-id="2928"
              width="38"
              height="38"
            >
              <path
                d="M732.16 563.84l21.76-301.44c-0.32-10.24 4.16-19.84 12.16-26.24l62.72-49.28a31.872 31.872 0 0 0-11.52-56L446.72 31.36c-25.6-6.72-47.68 18.24-38.08 42.88l29.76 74.24c3.84 9.28 2.88 20.16-2.56 28.8l-131.84 272c-2.88 4.48-6.72 8.32-11.2 10.88l-104.96 77.76c-21.44 16-15.04 49.6 10.88 56.64l552 147.84c25.92 7.04 48.32-19.2 37.76-43.52l-51.84-120a30.592 30.592 0 0 1-4.48-15.04z"
                fill="#CC5700"
                p-id="2929"
              ></path>
              <path
                d="M643.84 553.92a30.304 30.304 0 0 1-4.16-15.04l21.76-301.44c-0.32-10.24 4.16-19.84 12.16-26.24l113.28-88.96L446.72 31.36c-25.6-6.72-47.68 18.24-38.08 42.88l29.76 74.24c3.84 9.28 2.88 20.16-2.56 28.8l-131.84 272c-2.88 4.48-6.72 8.32-11.2 10.88l-104.96 78.08c-21.44 16-15.04 49.6 10.88 56.64l237.44 63.68-72.64 270.72c-5.76 21.12 7.04 43.2 28.16 48.96 21.12 5.76 43.2-7.04 48.96-28.16l72.64-270.72 208.64 56-78.08-181.44z"
                fill="#F66F00"
                p-id="2930"
              ></path>
              <path
                d="M766.08 236.16l62.72-49.28a31.872 31.872 0 0 0-11.52-56L446.72 31.36c-2.88-0.64-5.76-1.28-8.64-1.28-21.76 0-38.08 22.4-29.44 43.84l29.76 74.24c3.84 9.28 2.88 20.16-2.56 28.8l-131.84 272c-2.88 4.48-6.72 8.32-11.2 10.88L187.84 537.6c-21.44 16-15.04 49.6 10.88 56.64l237.44 63.68-72.64 270.72c-5.76 21.12 7.04 43.2 28.16 48.96a39.936 39.936 0 0 0 48.64-28.16l72.64-270.72 237.44 63.68c2.88 0.64 5.76 1.28 8.64 1.28 22.08 0 38.72-23.04 29.12-44.8l-51.84-120a30.304 30.304 0 0 1-4.16-15.04l21.76-301.44c-0.32-10.24 4.16-19.84 12.16-26.24zM417.6 943.04a15.744 15.744 0 0 1-19.52 11.2 16 16 0 0 1-11.2-19.52l72.64-270.72 30.72 8.32-72.64 270.72z m312.32-681.28l-21.76 300.48v2.56c0 1.6 0.64 3.52 0.64 5.12l-209.28-56c-6.4-1.6-13.12 2.24-14.72 8.64s2.24 13.12 8.64 14.72l224.96 60.16 48.32 111.36c1.28 2.56 0.96 5.12-0.64 7.36-0.64 0.96-2.88 3.84-6.4 3.84-0.64 0-1.6 0-2.24-0.32L204.8 571.2a7.872 7.872 0 0 1-2.56-14.08L306.24 480c7.36-4.48 13.76-10.88 18.24-18.24 0.32-0.64 0.96-1.28 1.28-2.24l131.52-271.04c8.64-14.72 9.92-32.96 3.52-48.96l-29.76-74.24c-0.96-2.56-0.96-5.12 0.64-7.36 0.64-0.96 2.88-3.52 6.4-3.52 0.64 0 1.6 0 2.24 0.32l370.88 99.52c4.16 0.96 5.44 4.16 5.76 6.08 0.32 1.92 0.64 5.12-2.88 8L752 216.96l-130.24-34.88a12.16 12.16 0 0 0-14.72 8.64c-1.6 6.4 1.92 13.12 8.64 14.72l120 32.32c-3.84 7.04-5.76 15.36-5.76 24z"
                fill="#662C00"
                p-id="2931"
              ></path>
              <path
                d="M420.48 454.72a16.096 16.096 0 0 1-14.72-22.4l88.96-208c3.52-8 12.8-11.84 21.12-8.32 8 3.52 11.84 12.8 8.32 21.12l-88.96 208c-2.56 5.76-8.64 9.6-14.72 9.6z"
                fill="#FFFFFF"
                p-id="2932"
              ></path>
            </svg>
          </h1>
          <h1
            class="font-serif text-xl font-extrabold text-center text-black  lg:text-3xl sm:text-2xl"
          >
            {{ scoped.item.title }}
          </h1>
          <h3
            class="mt-2 text-base font-thin text-gray-600 lg:text-xl sm:text-lg"
          >
            {{ scoped.item.info }}
          </h3>
        </div>
      </template>
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
.content {
  position: relative;
}
.content > .stick {
  position: absolute;
  right: -15px;
  top: -20px;
  transform: rotate(20deg);
}
</style>