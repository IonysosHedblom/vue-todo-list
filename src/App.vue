<template>
  <div id="app">
    <div class="container">
      <Header />
      <AddTodo v-on:add-todo="addTodo" />
      <Todos v-on:del-todo="deleteTodo" v-bind:todos="todos" />
    </div>
  </div>
</template>

<script>
import Todos from "./components/Todos";
import Header from "./components/Header";
import AddTodo from "./components/AddTodo";

export default {
  name: "App",
  components: {
    Todos,
    Header,
    AddTodo,
  },
  data() {
    return {
      todos: [
        {
          id: 1,
          title: "Code",
          completed: false,
        },
        {
          id: 2,
          title: "Eat",
          completed: false,
        },
        {
          id: 3,
          title: "Sleep",
          completed: false,
        },
      ],
    };
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter((todo) => todo.id !== id);
    },
    addTodo(newTodo) {
      this.todos = [...this.todos, newTodo];
    },
  },
};
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
ul {
  list-style: none;
}
.container {
  max-width: 800px;
  min-width: 450px;
  width: 60%;
  margin: 0 auto;
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
  background-color: #666;
}

@media screen and (max-width: 400px) {
  .container {
    width: 100%;
  }
}
</style>
