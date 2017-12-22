<template lang="jade">
  ul.list-unstyled
    li(v-for="todo in todos")
      todo-item(v-bind:todo="todo" v-bind:todos="todos")
</template>

<script>
  import TodoItem from './TodoItem'

  export default {
    name: 'TodoList',
    props: ['todos'],
    components: {
      TodoItem
    }
  }
</script>
