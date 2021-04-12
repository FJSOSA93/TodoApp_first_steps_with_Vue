<template>
    <div>
        <div class="todo-body" v-bind:class="{completed: todo.completed}">
            <input type="checkbox" v-bind:checked="todo.completed == true ? true : false " v-on:change="$emit('set-completed', todo.id)">
            {{todo.title}}
        </div>
        <div class="todo-actions">
            <button v-on:click = "$emit('delete-todo', todo.id)"> 
                Eliminar
            </button>
        </div>
    </div>
    
</template>

<script>
export default {
    name:'TodoItem',
    props : ['todo'],
    methods :{
        checkTodo () { // function to change the state of variable completed
            return false;
        }
    }
}
</script>


<style scoped>
.todo-body{
    color:black;
}
.completed {
    color:green;
}
</style>