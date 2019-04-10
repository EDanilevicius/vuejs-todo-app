<template>
  <div id="“app”">
    <AppHeader :date="headerDate">My Day!</AppHeader>
      <div class="todo-container">
        <ToDoList>
          <ToDoItem
          v-for="(todo, index) in todos"
          :key="todo + index"
          :todo="todo"
          :index="index"
          />
        </ToDoList>
      </div>
    <ToDoInput
    v-model="newToDo"
    @create="createTodo"
    />
  </div>
</template>
<script>
import AppHeader from '@/components/AppHeader'
import ToDoInput from '@/components/ToDoInput'
import ToDoList from '@/components/ToDoList'
import ToDoItem from '@/components/ToDoItem'
export default {
  name: 'App',
  components: {
    AppHeader,
    ToDoInput,
    ToDoList,
    ToDoItem
  },
  data: () => ({
    newToDo: null,
    headerDate: new Date('2018,10,5'),
    todos: []
  }),

  methods: {
    createTodo () {
      this.todos.push({
        title: this.newToDo,
        done: false
      })
      this.newToDo = null
    }
  }
}
</script>
<style lang="scss">
.todo-container {
  padding: 30px 15px;
}
</style>
