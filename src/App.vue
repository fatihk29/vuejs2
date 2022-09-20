<template>
  <div>
    <app-header v-bind:title="title"></app-header>
    <app-bases v-bind:info="info"></app-bases>
    <app-footer
      v-bind:title="title"
      v-on:changeTitle="updateTitle($event)"
    ></app-footer>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Footer from "./components/Footer.vue";
import Base from "./components/Base.vue";

export default {
  components: {
    "app-header": Header,
    "app-footer": Footer,
    "app-bases": Base
  },
  data() {
    return {
      info: [
        {
          name: "aquamarine",
          speciality: "Complex",
          show: false
        },
        {
          name: "blue",
          speciality: "soft",
          show: false
        },
        {
          name: "return",
          speciality: "null",
          show: false
        },
        {
          name: "green",
          speciality: "double",
          show: false
        }
      ],
      title: "Header Title",
      footerTitle: "Footer Title"
    };
  },
  methods: {
    updateTitle(data) {
      this.title = data;
    }
  }
};
</script>

<style scoped>
h1 {
  color: blueviolet;
}
</style>
