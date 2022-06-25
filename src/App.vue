<template>
  <div id="app">
    <TodoList/>
  </div>
</template>

<script>
import TodoList from './views/TodoList.vue'

export default {
  name: 'App',
  components: {
    TodoList
  }
}
</script>

<style>
body{
  background-color: #344fa1;
  font-family: 'Montserrat';
  font-size: 14px;
}
</style>
