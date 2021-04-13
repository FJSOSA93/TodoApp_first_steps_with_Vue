<template>
  <div class="container item-container">
    <div
      class="input-group mb-3 todo-body"
    >
      <div class="input-group-prepend">
        <div class="input-group-text">
          <input
            type="checkbox" 
            v-bind:checked="todo.completed == true ? true : false"
            v-on:change="$emit('set-completed', todo.id)"
          />
        </div>
      </div>
      <input type="text" class="form-control input-text" v-bind:class="{ completed: todo.completed }" :value="todo.title" disabled/>
    </div>
    <div class="todo-actions">
      <button class="btn btn-danger" v-on:click="$emit('delete-todo', todo.id)">
        Eliminar
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    checkTodo() {
      // function to change the state of variable completed
      return false;
    },
  },
};
</script>


<style scoped>
.todo-body {
  color: black;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
    Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  font-size: 20px;
}
.completed {
  text-decoration: line-through;
  margin-left:10px;
  font-weight: bold;
  background: rgb(54,184,17);
  background: linear-gradient(90deg, rgba(54,184,17,0.7595413165266106) 5%, rgba(3,223,36,0.9472163865546218) 87%, rgba(0,255,248,1) 96%);
}
.item-container{
    display: flex;
}
.input-text{
    margin-right: 10px;
}

</style>