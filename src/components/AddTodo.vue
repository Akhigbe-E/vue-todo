<template>
  <div>
    <form @submit="addTodo">
      <input
        type="text"
        v-model="title"
        id="todoTitle"
        placeholder="Enter todo"
        class="todo-input"
      />
      <input type="submit" value="Submit" class="btn" />
    </form>
  </div>
</template>

<script>
  //   import { v4 as uuidv4 } from "uuid";
  export default {
    name: "AddTodo",
    data() {
      return {
        title: "",
      };
    },
    methods: {
      addTodo(e) {
        e.preventDefault();
        const newTodo = {
          title: this.title,
          completed: false,
        };
        this.$emit("add-todo", newTodo);
        this.title = "";
      },
    },
  };
</script>

<style scoped>
  form {
    display: flex;
  }
  .todo-input {
    flex: 10;
    padding: 3px 2px;
  }
  .btn {
    flex: 2;
  }
</style>
