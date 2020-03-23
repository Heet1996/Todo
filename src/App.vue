<template>
  <div id="app" class="app-layout">
     <Header />
      <Todo 
      v-bind:todos="todo" 
      v-on:del-item="deleteItem"
      />
      <AddToDo v-on:addToDo="addToDo" />
  </div>
</template>

<script>

import Todo from './components/Todo';
import Header from './components/Layout/Header';
import AddToDo from './components/AddToDo';
export default {
  name: 'App',
  components: {
    Todo:Todo,
    Header:Header,
    AddToDo:AddToDo
  },
  methods:{
    deleteItem(id)
    { 
      console.log(id);
      this.todo=this.todo.filter((todo)=>todo.id!=id);
    },
    addToDo(newToDo)
    {
      this.todo=[...this.todo,newToDo];
    }
  },
  data()
  {
    return {
      todo:[
        {
          id:1,
          completed:true,
          title:"To do one"
        },
            {
          id:2,
          completed:false,
          title:"To do two"
        },
            {
          id:3,
          completed:true,
          title:"To do three"
        }

      ]
      }
  }
}
</script>

<style>
*
{
  box-sizing: border-box;
  margin:0;
  padding: 0;  
}
body
{
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
  
}
.app-layout
{
  width:60%;
  position: absolute;
  top: 20%;
  left: 20%;  
}
</style>
