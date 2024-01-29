
<template>

    <div
      class="todo_item"
      @dblclick="removeTodo"
      @click="changeTodo"
      :style="{ backgroundColor: completed ? 'green' : 'red' }"
    >
      <h1>{{ title }}</h1>
    </div>

  </template>
  
  <script>

  export default {

    props: ['title', 'completed', 'id'],
    methods: {
      removeTodo() {
        this.$emit('remove-todo', this.id);
       },
      changeTodo() {
        this.$emit('change-todo', this.id);
       }
      }
  }
  </script>
  
  <style>

  .todo_item {
    display: flex;
    flex-direction: column;
    margin: 20px 170px;
    padding: 10px;
    outline: 2px solid black;
    box-shadow: 5px 5px 5px black;
  }
  
  </style>
  