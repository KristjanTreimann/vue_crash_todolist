<template>
  <div id="app">

    <AddTodo v-on:add-todo="addTodo"/>
    <Todos v-bind:todos="todos" v-on:del-todo="deleteTodo"/>

  </div>
</template>

<script>
import Todos from '../components/Todos' // .. moves back two folders
//import Header from '../components/layout/Header' no need when routing
import AddTodo from '../components/AddTodo'
import axios from 'axios'

export default {
  name: 'Home',
  components: { Todos, AddTodo },
  data() {
    return {
      todos: [] // empty array to begin with
    }
  },
  methods: {
    deleteTodo(id) {

      axios.delete(`https://jsonplaceholder.typicode.com/todos/${id}`)
        .then( this.todos = this.todos.filter(todo => todo.id !== id)) //delete request need id and to put a variable use backtick
     //.then(res => this.todos = this.todos.filter(todo => todo.id !== id))
     //this.todos = this.todos.filter(todo => todo.id !== id)
        .catch(err => console.log(err))
    },
    addTodo(newTodo) {
      const { title, completed } = newTodo // use only specific data from res

      axios.post('https://jsonplaceholder.typicode.com/todos', {
        title, //we need to add another peremiter with the data we are sending
        completed //and also completed which we pulled from this newTodo
      }) // so we are sending this data along and thats gonna give us a promise back
        .then(res => this.todos = [...this.todos, res.data]) //instead of newTodo, we use a data it gives us back
        .catch(err => console.log(err))
      //this.todos = [...this.todos, newTodo]
    }
  },
  created() {
    // Axios get request
    axios.get('https://jsonplaceholder.typicode.com/todos?_limit=5') // --> returns promise
    .then(res => this.todos = res.data) // handles promise
    .catch(err => console.log(err))
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

  .btn {
    display: inline-block;
    border: none;
    background: #555;
    color: #fff;
    padding: 7px 20px;
    cursor: pointer;
  }

  .btn:hover {
    background: #666;
  }
</style>
