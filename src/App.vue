<script>
  import HelloWorld from './components/HelloWorld.vue'
  import TodoList from './components/TodoList.vue'
  
  export default {
    components: { HelloWorld, TodoList},
    data() {
      return {
        helloworldPage: true
      }
    },
    methods: {
      showTodo() {
        this.helloworldPage = false
      },
      showHW() {
        this.helloworldPage = true
      }
    }
  }
</script>

<template>   
 
  <a href="https://vuejs.org/" target="_blank"><img src="./assets/vue.svg" class="logo vue" alt="Vue logo" /></a>
  
  <div class="d-flex justify-content-center">
    <button @click="showHW" class="btn-primary m-3">Hello World</button>
    <button @click="showTodo" class="btn-primary m-3">Todo list</button>
  </div>
  
  <HelloWorld v-if="helloworldPage" />
  <TodoList v-else/>

</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}
</style>
