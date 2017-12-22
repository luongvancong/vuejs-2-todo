<template lang="jade">
  div.container
    todo-input(v-bind:todos="todos")
    todo-list(v-bind:todos="todos")
</template>

<script>
  import TodoInput from './TodoInput'
  import TodoList from './TodoList'
  export default {
    name: 'Todo',
    data: function () {
      return {
        todos: []
      }
    },
    components: {
      'todo-input': TodoInput,
      'todo-list': TodoList
    }
  }
</script>