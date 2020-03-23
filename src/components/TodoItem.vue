<template>
    <div class="todo-item">
        <p class="todo-item_layout">
          <span v-bind:class="{'is-completed':todoItem.completed}">
          <input type="checkbox" v-on:change="markComplete" />  
          {{todoItem.title}}
          </span>
          <button class="del" @click="$emit('del-item')">x</button>
        </p>
        
    </div>
</template>

<script>

export default {
    name:"ToDoItem",
    props:["todoItem"], 
    methods:{
        markComplete(){
            this.todoItem.completed=!this.todoItem.completed;
        }   
    }
}
</script>

<style scoped>
.todo-item
{
    background-color :#f4f4f4;
    padding :10px;
    border-bottom: 1px #ccc dotted;
    display: flex;
    width: 100%;
}
.is-completed{
    text-decoration:line-through
}
.todo-item_layout
{
    display: flex;
    flex-direction: row;
    justify-content:space-between;
    align-items: center;
    width: 100%;

}
.del
{
    background: crimson;
    color:whitesmoke;
    outline: none;
    border: none;
    border-radius:40% ;
    font-size: 1rem;
    padding: 0.5rem;
    cursor: pointer;
    text-decoration: none;

}
</style>