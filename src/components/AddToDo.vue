<template>
    <div>
        <form @submit="addToDo">
            <input type="text" placeholder="Add Todo Items" v-model="title"/>
            <button type="submit">Add</button>

        </form>
    </div>
</template>
<script>
import {v4 as uuidv4} from 'uuid';
export default {
    name:"AddToDo",
    data()
    {
        return{
            title:""
        }
    },
    methods:{
        addToDo(e){
            e.preventDefault();
            let newToDo={
                id:uuidv4(),
                completed:false,
                title:this.title
            }
            this.$emit('addToDo',newToDo);
            this.title='';
        }
    }

}
</script>
<style scoped>

</style>>

