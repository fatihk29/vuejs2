<template>
  <div id="basesID">
    <h1>List of items</h1>
    <ul>
      <li v-for="item in info" v-on:click="item.show = !item.show">
        <h2>{{ item.name }}</h2>
        <h3 v-show="item.show">{{ item.speciality }}</h3>
      </li>
    </ul>
    <button v-on:click="deleteInfo">Delete Info</button>
  </div>
</template>

<script>
export default {
  props: {
    info: {
      type: Array,
      required: true
    }
  },
  data() {
    return {};
  },
  methods: {
    deleteInfo() {
      this.info.pop();
    }
  },
  // lifecycle hooks
  beforeCreate() {

    alert("beforeCreate");
  },
  created() {
    // good for catching data
    alert("created");
  },
  beforeMount() {
    alert("beforeMount");
  },
  mounted() {
    // good for manipulating data
    alert("mounted");
  },
  beforeUpdate() {
    alert("beforeUpdate");
  },
  updated() {
    alert("updated");
  }
};
</script>

<style scoped>
#basesID {
  width: 100%;
  max-width: 1200px;
  margin: 40px auto;
  padding: 0 20px;
  box-sizing: border-box;
}
ul {
  display: flex;
  flex-wrap: wrap;
  list-style-type: none;
  padding: 0;
}
li {
  flex-grow: 1;
  flex-basis: 300px;
  text-align: center;
  padding: 30px;
  border: 1px solid #333;
}
</style>
