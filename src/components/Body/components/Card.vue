<template>
  <div class="flex flex-col h-full justify-between">
    <img class="rounded-3xl" :src="`${chapter.img}`" :alt="`${chapter.name}`" />
    <div class="flex flex-col mx-auto">
      <div class="mx-auto mt-5 text-3xl">{{ chapter.name }}</div>
      <div class="mx-auto mt-3 text-3xl">
        {{ chapter.status }}
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import { Chapter } from "../../../models/chapter";

export default defineComponent({
  name: "Card",
  props: {
    chapter: {
      required: true,
      type: Chapter,
    },
  },
});
</script>
