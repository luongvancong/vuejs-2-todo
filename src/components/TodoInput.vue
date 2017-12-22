<template lang="jade">
  div
    input(type="text" class="form-control" v-on:keyup.13="onKeyUp")
</template>

<script>
  export default {
    name: 'TodoInput',
    props: ['todos'],
    methods: {
      onKeyUp: function (e) {
        this.todos.push({
          text: e.currentTarget.value,
          checked: false
        })
        e.currentTarget.value = ''
      }
    }
  }
</script>