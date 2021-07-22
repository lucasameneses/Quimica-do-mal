<template>
  <Header></Header>
  <Body></Body>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Header from "./components/Header/Header.vue";
import Body from "./components/Body/Body.vue";
import "./index.css";

export default defineComponent({
  name: "App",
  components: {
    Header,
    Body,
  },
});
</script>
