<template lang="jade">
  div
    input(type="checkbox" v-on:change="onChange(todo)")
    span(:class="todo.checked ? 'strike' : ''") {{ todo.text }}
    small(v-on:click="done(todo)") Done
</template>

<script>
  export default {
    name: 'TodoItem',
    props: ['todo', 'todos'],
    methods: {
      onChange: function (todo) {
        todo.checked = !todo.checked
      },
      done (todo) {
        let index = this.todos.indexOf(todo)
        this.todos.splice(index, 1)
      }
    }
  }
</script>

<style scoped>
  input {
    margin-right: 5px;
  }
  span {
    display: inline-block;
    padding: 0 10px;
  }
  .strike {
    text-decoration: line-through;
  }
  small {
    font-size: 10px;
    font-weight: bold;
    text-decoration: underline;
    cursor: pointer;
  }
</style>