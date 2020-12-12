<template>
  <div>
    <ul>
      <li v-bind:key="index" v-for="(todo, index) in todos"><TodoItem v-on:del-todo="$emit('del-todo', todo.id)" v-bind:todo="todo" /></li>
    </ul>
  </div>
</template>

<script>
import TodoItem from './TodoItem';
export default {
  props: ['todos'],

  components: {
    TodoItem
  }
}
</script>

<style scoped>

</style>