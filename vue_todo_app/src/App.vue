<template>
<div>
    <div id="header"></div>
    
    <div id="main-container">
      <h2>Todos</h2>
      <Todos v-bind:todoList = 'copyTodos' v-on:delete-todo = "deleteTodo" v-on:set-completed = "setCompleted"/>
    </div>
</div>
</template>

<script>
//import HelloWorld from './components/HelloWorld.vue'
//import Search from "./components/Search";
//import TodoAdd from "./components/TodoAdd";
import Todos from "./components/Todos";

export default {
  name: "App",
  components: {
    //Search,
    Todos,
    //TodoAdd,
  },
  data() {
    return {
      todos: [
        {
          id: 0,
          title: "Terminar ticket",
          completed: true,
        },
        {
          id: 1,
          title: "Terminar algo1",
          completed: false,
        },
        {
          id: 2,
          title: "Terminar algo2",
          completed: false,
        }
      ],
      copyTodos: []
    };
  },
  methods:{
    deleteTodo(id){
      this.todos = this.todos.filter(todo => todo.id != id);
      this.copyTodos = [... this.todos];
      console.log("event delete ", id)
    },
    setCompleted(id){  // put the task like completed
      this.copyTodos[id].completed = !this.copyTodos[id].completed;
    }
  },
  created() {
    this.copyTodos = [... this.todos];
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
