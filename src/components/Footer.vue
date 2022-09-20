<template>
  <footer>
    <p v-on:click="changeTitle">{{ title }}, {{ copyright }}</p>
  </footer>
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
    return {
      copyright: "Copyright © 2022"
    };
  },
  methods: {
    changeTitle() {
      //this.$emit("changeTitle", "Vuew");
      this.title = 'Vuew via EvetBus'
      bus.$emit('titleChanged', 'Vuew via EvetBus')
    }
  }
};
</script>

<style scoped>
footer {
  background: #222;
  padding: 6px;
}
p {
  color: lightcoral;
  text-align: center;
}
</style>
