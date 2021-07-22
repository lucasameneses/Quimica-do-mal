<template>
  <div class="flex flex-wrap bg-gray-600 gap-3">
    <div
      class="bg-gray-300 p-10, rounded-3xl shadow-2xl mx-auto w-80"
      v-for="(chapter, index) in chapters"
      :key="index"
    >
      <Card :chapter="chapter"></Card>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import axios from "axios";
import Card from "./components/Card.vue";
import { Chapter } from "../../models/chapter";

export default defineComponent({
  name: "Body",
  components: { Card },
  data() {
    return {
      chapters: [] as Chapter[],
    };
  },
  mounted() {
    axios
      .get("https://www.breakingbadapi.com/api/characters")
      .then((response) => {
        response.data.forEach(async (resp: any) => {
          this.chapters.push(Object.assign(new Chapter(), resp));
        });
        console.log(this.chapters);
      });
  },
});
</script>
