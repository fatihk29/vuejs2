<template>
  <div id="add-blog">
    <h2>Add a New Blog Post</h2>
    <form action="">
      <label>Blog Title:</label>
      <input type="text" v-model.trim()="blog.title" required />
      <label for="">Blog Content</label>
      <textarea v-model="blog.content"></textarea>
      <div id="checkboxes">
        <label for="">Ninjas</label>
        <input type="checkbox" value="ninjas" v-model="blog.categories" />
        <label for="">Wizard</label>
        <input type="checkbox" value="wizard" v-model="blog.categories" />
        <label for="">Mario</label>
        <input type="checkbox" value="mario" v-model="blog.categories" />
        <label for="">Cheese</label>
        <input type="checkbox" value="cheese" v-model="blog.categories" />
      </div>
    </form>
    <div id="preview">
      <h3>Preview blog</h3>
      <p>Blog Title: {{ blog.title }}</p>
      <p>Blog Content:</p>
      <p>{{ blog.content }}</p>
      <p>Blog Categories</p>
      <ul>
        <li v-for="category in blog.categories">
          {{ category }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  components: {},
  data() {
    return {
      blog: { title: "", content: "", categories: [] }
    };
  },
  methods: {}
};
</script>

<style scoped>
#add-blog * {
  box-sizing: border-box;
}
#add-blog {
  margin: 20px auto;
  max-width: 500px;
}
label {
  display: block;
  margin: 20px 0 10px;
}
input[type="text"],
textarea {
  display: block;
  width: 100%;
  padding: 8px;
}
#preview {
  padding: 10px 20px;
  border: 1px dotted #ccc;
  margin: 30px 0;
}
h3 {
  margin-top: 10px;
}
#chechboxes {
  display: inline-block;
  margin-right: 10px;
}
#checkboxes label {
  display: inline-block;
}
</style>
