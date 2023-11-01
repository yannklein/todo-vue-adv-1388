<script>
import TodoItem from './TodoItem.vue';
export default {
  components: {
    TodoItem
  },
  data() {
    return {
      todos: [
        { title: 'Code a to-do list', done: false },
        { title: 'Eat breakfast', done: true },
        { title: 'Do some exercise', done: false },
        { title: 'Water the plants', done: true },
      ],
      newTodo: null,
    };
  },
  methods: {
    addTodo() {
      if (this.newTodo) {
        this.todos.push({ title: this.newTodo.trim(), done: false });
        this.newTodo = null;
      }
    },
    deleteTodo(index) {
      this.todos.splice(index, 1);
    },
  },
};
</script>

<template>
  <div>
    <h1 class="mb-3">🗒 My Todo List</h1>
    <div id="todosContainer" v-cloak>
      
      <div v-for="todo in todos" class="shadow-sm rounded px-4 py-3 mb-2 border d-flex justify-content-between" :key="todo.title">
        <TodoItem :todo="todo" />
      </div>
      
      <div class="input-group mb-3 mt-5">
        <input v-model="newTodo" type="text" class="form-control p-2 rounded" placeholder="Your task goes here"/>
        <button @click="addTodo" class="btn btn-primary" type="button">Add</button>
      </div>
    </div>
  </div>
</template>


<style lang="scss" scoped></style>
