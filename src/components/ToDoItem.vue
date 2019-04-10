<template>
  <li
    class="todo-list-item">
    #{{index + 1}} {{todo.title}}
  </li>
</template>

<script>
export default {
  name: 'ToDoItem',
  props: {
    todo: {
      type: Object,
      required: true,
      default: () => ({
        title: null,
        done: false
      })
    },
    index: {
      type: String,
      required: true
    }
  }
}
</script>

<style lang="scss">
  .todo-list-item {
    width: 100%;
    border: 1px solid rgba(black, 0.51);
    border-radius: 10px;
    padding: 15px;
    margin-bottom: 15px;
  }
</style>
