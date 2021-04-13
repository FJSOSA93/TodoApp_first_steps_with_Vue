<template>
  <div id="add-container" class="container">
    <form action="" v-on:submit="addTodo">
      <div class="input-group mb-3">
        <div class="input-group-prepend">
        </div>
        <input
          type="text"
          class="form-control"
          v-model="title"
        />
      </div>
    </form>
  </div>
</template>
<script>
import {uuid} from 'vue-uuid'
export default {
  name: "TodoAdd",
  data(){
      return {
          title:''
      }
  },
  methods:{
      addTodo(e){
          e.preventDefault();
          const newTodo = {
              id:uuid.v4(),
              title:this.title,
              completed:false
          }
          this.title = '';
          this.$emit ('add-todo',newTodo);
      }
  }
};
</script>

<style scoped>
#add-container {
  padding: 10px;
}
</style>