<template>
  <div class="todo-list">
    <ul class="todo-list__list"></ul>
    <div class="todo-list__input">
      <input
        :value="value"
        class="todo-list__input-textfield"
        placeholder="Add To Do..."
        type="text"
        @input="handleInput"
      >
      <button class="todo-list__input-button" type="button" @click="handleClick">Create</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ToDoInput',
  props: {
    value: {
      type: String
    }
  },
  methods: {
    handleInput (event) {
      this.$emit('input', event.target.value)
    },
    handleClick (event) {
      this.$emit('create', event)
    }
  }
}
</script>

<style lang="scss">
.todo-list {
  padding: 30px 15px;
  &__list {
    list-style: none;
    padding: 0;
    margin: 0;
  }
  &__item {
    width: 100%;
    border: 1px solid rgba(black, 0.51);
    border-radius: 10px;
    padding: 15px;
  }
  &__input {
    display: flex;
    align-items: center;
    width: 100%;
    border: 1px solid rgba(black, 0.51);
    border-radius: 10px;
    padding: 0 15px;
    &-textfield {
      width: 100%;
      padding: 15px 0;
      margin-right: 15px;
      font-size: 14px;
      border: 0;
      outline: 0;
    }
    &-button {
      -webkit-appearance: none;
      border: 0;
      border-radius: 30px;
      background-color: royalblue;
      color: white;
      padding: 7.5px 15px;
      text-transform: uppercase;
      font-size: 12px;
      outline: 0;
      &:hover {
        cursor: pointer;
        opacity: 0.7;
      }
    }
  }
}
</style>
