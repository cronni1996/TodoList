<template>
  <div >
    <h2 class="title">ToDo application </h2>
    <addTodo
        @add-Todo="addTodo"
    />
    <hr>

    <TodoList
        v-bind:todos="todos"
        @remove-todo="removeToDo"
    />
  </div>
</template>

<script>
import TodoList from "@/components/TodoList";
import addTodo from "@/components/addTodo";
import AddTodo from "@/components/addTodo";

export default {
  name: 'App',
  data(){
    return{
      todos: [
        {id:1, title:'заебаться', completed:false},
        {id:2, title:'проорать стену', completed:false},
        {id:3, title:'прогореть', completed:false},
        {id:4, title:'лечь спать ', completed:false},
      ]
    }
  },
  methods:{
    removeToDo(id){
      this.todos = this.todos.filter(t => t.id !== id)
    },
    addTodo(todo){
      this.todos.push(todo)
    }
  },
  components: {AddTodo, TodoList}
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
