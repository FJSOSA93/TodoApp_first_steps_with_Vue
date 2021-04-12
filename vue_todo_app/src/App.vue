<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <HelloWorld msg="Welcome to Your Vue.js App" />
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
import Search from "./components/Search";
import TodoAdd from "./components/TodoAdd";
import Todos from "./components/Todos";

export default {
  name: "App",
  components: {
    Search,
    Todos,
    TodoAdd,
  },
  data() {
    return {
      todos: [
        {
          id: 0,
          title: "Terminar ticket",
          complete: false,
        },
        {
          id: 0,
          title: "Terminar algo1",
          complete: false,
        },
        {
          id: 0,
          title: "Terminar algo2",
          complete: false,
        }
      ],
      copyTodos: []
    };
  },
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
</style>
