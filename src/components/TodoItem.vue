<template>
  <div class=" w-100">
    <div class="d-flex justify-content-between w-100">
      <div class="d-flex">
        <input class="d-flex form-check-input me-1" type="checkbox" v-model="todo.done"/>
        <div v-bind:class="{ 'text-decoration-line-through': todo.done, 'text-secondary': todo.done,}">
          {{ todo.title }}
        </div>
      </div>
      <button type="button" class="btn-close" @click="deleteTodo(index)"></button>
    </div>
  </div>
</template>

<script>
  export default {
    props: {
      todo: Object
    }
  }
</script>

<style lang="scss" scoped>

</style>