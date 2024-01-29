
<template>

    <div class="input_elem">
      <input @keydown="handleKey" />
    </div>

  </template>
  
  <script>
  export default {


    methods: {
      handleKey(event) {
         if (event.key === 'Enter') {
          this.$emit('add-new-todo', event.target.value);
          event.target.value = '';
          }
        }
     }
  }
  </script>
  
  <style>

  .input_elem {
    display: flex;
    justify-content: center;
    margin: 20px 400px;
  }
  
  .input_elem > input {
    width: 100%;
    box-shadow: 5px 5px 5px black;
  }
  
  </style>
  