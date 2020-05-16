<template>
  <div class="Deals">
    <h1 id="test">Test Deals Page</h1>
    <ul>
      <li v-for="todo of todos" :key="todo.id">{{ todo.title }}</li>
    </ul>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "Deals",
  props: {},

  data() {
    return {
      todos: [],
    };
  },

  //Used JsonPlaceHolder to test axios
  async created() {
    try {
      const res = await axios.get("https://jsonplaceholder.typicode.com/posts");

      this.todos = res.data;
      console.log(res);
    } catch (e) {
      console.error(e);
    }
  },
};
</script>

<style>
#test {
  color: red;
}
</style>
