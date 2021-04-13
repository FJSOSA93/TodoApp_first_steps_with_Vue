<template>
    <div>
        <div v-bind:key="todo.id" v-for="todo in todoList" class="container-task">
            <TodoItem v-bind:todo="todo" v-on:delete-todo="$emit('delete-todo',todo.id)" v-on:set-completed="$emit('set-completed',todo.id)"  />
        </div>
    </div>
</template>
<script>
import TodoItem from './TodoItem'
export default {
    name : 'Todos',
    props: ['todoList'],
    components:{TodoItem}
}
</script>

<style scoped>
.container-task{
    text-align: center;
}
</style>
