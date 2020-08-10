<template>
  <div id="app">
    <Header />
    <AddTodo @add-todo="addTodo" />
    <div>
      <Todos v-bind:todos="todos" @del-todo="deleteTodo" />
    </div>
  </div>
</template>

<script>
  import Todos from "./components/Todos";
  import AddTodo from "./components/AddTodo";
  import Header from "./components/layout/Header";
  import axios from "axios";

  export default {
    name: "App",
    components: {
      Todos,
      Header,
      AddTodo,
    },
    data() {
      return {
        todos: [],
      };
    },
    methods: {
      deleteTodo(todoId) {
        axios
          .delete(`https://jsonplaceholder.typicode.com/todos/${todoId}`)
          .then(
            () => (this.todos = this.todos.filter(({ id }) => id !== todoId))
          )
          .catch((err) => alert(err.toString()));
      },
      addTodo({ title, completed }) {
        axios
          .post(`https://jsonplaceholder.typicode.com/todos`, {
            title,
            completed,
          })
          .then(({ data }) => (this.todos = [...this.todos, data]))
          .catch((err) => alert(err.toString()));
      },
    },
    created() {
      axios
        .get(`https://jsonplaceholder.typicode.com/todos?_limit=5`)
        .then(({ data }) => (this.todos = data))
        .catch((err) => alert(err.toString()));
    },
  };
</script>

<style>
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }
  body {
    font-family: Raleway, Arial, Helvetica, sans-serif;
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
