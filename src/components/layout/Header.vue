<template>
  <div>
    <header class="todo-header">
      <h1>Basic Todos</h1>
      <div>
        <router-link to="/">Home</router-link> |
        <router-link to="/about">About</router-link>
      </div>
    </header>
  </div>
</template>

<script>
  export default {
    name: "Header",
  };
</script>

<style scoped>
  .todo-header {
    padding: 15px 0px;
    background: #02040a;
    width: 100%;
    display: block;
    color: white;
    text-align: center;
  }
  .todo-header a {
    color: #fff;
    padding-right: 5px;
    text-decoration: none;
  }
</style>
