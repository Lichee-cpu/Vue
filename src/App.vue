<template>
  <div id="app">
    <h2>Add Todo </h2>
    <Addtodo v-on:add-todo="addtodo"/>
    <Todos v-bind:todos="todos" v-on:delete-todo="deleteTodo"/>
  </div>
</template>

<script>
import Todos from './components/Todo/Todos.vue'
import Addtodo from './components/Todo/Addtodo.vue'
export default {
  name: 'App',
  components: {
    Addtodo,
    Todos
  },
data(){
    return{
        todos:[
            {
                id:1,
                title:'todo one',
                completed:false
            },
            {
                id:2,
                title:'todo two',
                completed:true
            }
        ]
    };
},
methods:{
  addtodo(todo){
    this.todos.unshift(todo)
  },
  deleteTodo(id){
    this.todos = this.todos.filter(todo=>todo.id !== id)
  }
}   
}
</script>

<style>
body{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  color: #2c3e50;
  margin: 0;
  padding: 0;

}
h2{
  margin: 0;
  padding: 5px 10px;
}

</style>
