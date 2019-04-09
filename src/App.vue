<template>
  <div id="“app”">
    <AppHeader :date="headerDate">My Day!</AppHeader>
    {{newToDo}}
    <ToDoInput v-model="newToDo"></ToDoInput>
  </div>
</template>
<script>
import AppHeader from "@/components/AppHeader";
import ToDoInput from "@/components/ToDoInput";
export default {
  name: "App",
  components: {
    AppHeader,
    ToDoInput
  },
  data: () => ({
    newToDo: null,
    headerDate: new Date("2018,10,5")
  })
};
</script>
<style lang=“scss”>
</style>
