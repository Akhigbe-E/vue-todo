<template>
  <div>
    <form @submit="addTodo">
      <label for="todoTitle">Title</label>
      <input type="text" v-model="title" id="todoTitle" placeholder="Enter todo" class="todo-input" />
      <input type="submit" value="Submit" class="btn" />
    </form>
  </div>
</template>

<script>
export default {
  name: "AddTodo",
  data() {
    return {
      title: "",
    };
  },
    methods:{
        addTodo(){
            const newTodo = {
                id:
            }
        }
    }
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