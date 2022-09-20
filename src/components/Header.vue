<template>
  <header>
    <h1>{{ title }}</h1>
  </header>
</template>

<script>
import { bus } from "../main";

export default {
  props: {
    title: {
      type: String,
      required: true
    }
  },
  data() {
    return {};
  },
  created() {
    bus.$on("titleChanged", data => {
      this.title = data;
    });
  }
};
</script>

<style scoped>
header {
  background: lightgreen;
  padding: 10px;
}
h1 {
  color: #222;
  text-align: center;
}
</style>
