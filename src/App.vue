<template>
  <div id="app">
    <!-- pass data from return/todos("todos") and we call it todos -->
    <todos v-bind:todos="todos" v-on:del-todo="deleteTodo"/>
  </div>
</template>

<script>
import Todos from './components/Todos.vue'

export default {
  name: 'app',
  components: {
    Todos
    
  },
  data(){
    return{
      todos: [
        {
          id:1,
          title:"Todo one",
          completed:false
        },
        {
          id:2,
          title:"Todo two",
          completed:true
        },
        {
          id:1,
          title:"Todo three",
          completed:false
        }
      ]
    }
  },
  methods:{
     deleteTodo(id) {
       this.todos = this.todos.filter(todo => todo.id !== id);
     }
  }
}
</script>

<style>
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }
  body {
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.4;
  }
</style>



