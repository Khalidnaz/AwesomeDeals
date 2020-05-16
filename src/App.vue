<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    
    <h1 id="axiosTest">Test for Axios</h1>
    <ul>
      <li v-for="todo of todos" :key="todo.id">{{todo.title}}</li>
    </ul>
  
  
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import axios from 'axios'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data() {
    return {
      todos: []
    };
  },

//Used JsonPlaceHolder to test axios
  async created() {
    try {
      const res = await axios.get('https://jsonplaceholder.typicode.com/posts')

      this.todos = res.data;
      console.log(res);
    } catch (e) {
      console.error(e);
    }
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

#axiosTest {
  color:red
}
</style>
