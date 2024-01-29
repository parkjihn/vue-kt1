

<template>

  <div>
    
    <AddToDo @add-new-todo="addNewTodo" />
    <ToDoList
      :todos="todos"
      @remove-todo="removeTodo"
      @change-todo="changeTodo"
    />
  </div>

</template>

<script>
import AddToDo from './components/AddToDo.vue';
import ToDoItem from './components/ToDoItem.vue';
import ToDoList from './components/ToDoList.vue';



export default {

  components: {
    AddToDo,
    ToDoItem,
    ToDoList
  },

  data() {
    return {
      todos: [
        { id: 1, title: 'Позавтракать', completed: true },
        { id: 2, title: 'Почистить огурцы', completed: false },
        { id: 3, title: 'Помыть кота', completed: true },
      ]
    };
  },

  methods: {
    removeTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    },
    changeTodo(id) {
      this.todos = this.todos.map(todo => {
        if (todo.id === id) {
          return { ...todo, completed: !todo.completed };
        }
        return todo;
      });
    },

    addNewTodo(title) {
      const newTodo = {
        id: Date.now(),
        title,
        completed: false
      };
      this.todos.push(newTodo);
    }
  }
}


</script>