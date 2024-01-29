
<template>

    <div>
      <ToDoItem
        v-for="todo in todos"
        :key="todo.id"
        :id="todo.id"
        :title="todo.title"
        :completed="todo.completed"
        @remove-todo="removeTodo"
        @change-todo="changeTodo"
      />
 </div>

  </template>
  
  <script>

  import ToDoItem from './ToDoItem.vue';
  
  export default {
    components: {
      ToDoItem
    },
    props: ['todos'],
    methods: {
      removeTodo(id) {
        this.$emit('remove-todo', id);
      },
      changeTodo(id) {
        this.$emit('change-todo', id);
      }
    }
  }

  </script>
  