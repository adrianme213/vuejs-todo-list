<!-- Template area is the visual part of the component -->
<template>
  <div>
    <p>Completed Tasks: {{todos.filter(todo => {return todo.done === true}).length}}</p>
    <p>Pending Tasks: {{todos.filter(todo => {return todo.done === false}).length}}</p>
    <todo v-on:delete-todo="deleteTodo" v-for="todo in todos" v-bind:todo="todo"></todo>
  </div>
</template>

<!-- Behavior, events, and data storage for the template are handled by the class -->
<script type="text/javascript">
import Todo from './Todo';
export default {
  // declares the properties this component will accept
  props: ['todos'],
  components: {
    Todo,
  },
  methods: {
    deleteTodo(todo) {
      const todoIndex = this.todos.indexOf(todo);
      this.todos.splice(todoIndex, 1);
    }
  }
};

</script>

<!-- Style section improves appearance of the template -->
<style>
</style>
