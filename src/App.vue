<template>
  <div>
    <todo-list v-bind:todos="todos"></todo-list>
    <create-todo v-on:create-todo="createTodo"></create-todo>
  </div>
</template>

<script>
import SweetAlert from 'sweetalert';
import TodoList from './components/TodoList';
import CreateTodo from './components/CreateTodo';

export default {
  name: 'app',
  components: {
    TodoList,
    CreateTodo,
  },
  // data function avails data to the template
  // The todos will now be available to components
  data() {
    return {
      todos: [{
        title: 'Todo A',
        project: 'Project A',
        done: false,
      }, {
        title: 'Todo B',
        project: 'Project B',
        done: true,
      }, {
        title: 'Todo C',
        project: 'Project C',
        done: false,
      }, {
        title: 'Todo D',
        project: 'Project D',
        done: false,
      }],
    };
  },
  methods: {
    createTodo(title) {
      this.todos.push({
        title,
        done: false,
      });
      SweetAlert('Success!', 'To-Do Created!', 'Success');
    },
  },
};
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
