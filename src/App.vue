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
        this.todos = this.todos.filter(({ id }) => id !== todoId);
      },
      addTodo({ title, completed }) {
        axios
          .post(`https://jsonplaceholder.typicode.com/todos`, {
            title,
            completed,
          })
          .then((res) => (this.todos = [...this.todos, newTodo]))
          .catch((err) => console.log(err));
      },
    },
    created() {
      axios
        .get(`https://jsonplaceholder.typicode.com/todos?_limit=5`)
        .then(({ data }) => (this.todos = data))
        .catch((err) => console.log(err));
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
