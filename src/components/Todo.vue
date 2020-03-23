<template>
    <div>
        <div v-bind:key="todo.id" v-for="todo in todos">
               <TodoItem 
               v-bind:todoItem="todo"
               v-on:del-item="$emit('del-item',todo.id)"
               />
        </div>
    </div>
</template>
<script>
import TodoItem from './TodoItem';
export default {
    name:"Todos",
    props:["todos"],
    components:{
        TodoItem:TodoItem
    }
}
</script>
<style scoped>

</style>