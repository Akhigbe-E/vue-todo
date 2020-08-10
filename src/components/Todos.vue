<template>
  <div>
    <div v-bind:key="todo.id" v-for="todo in todos">
      <TodoItem v-bind:todo="todo" @del-todo="$emit('del-todo', todo.id)" />
    </div>
  </div>
</template>

<script>
import TodoItem from "./TodoItem";
export default {
  name: "Todos",
  props: ["todos", "del-todo"],
  components: {
    TodoItem,
  },
};
</script>

<style scoped>
</style>