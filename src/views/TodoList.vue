<template>
  <div class="container">
   <TodoAdd/>
  </div>
</template>

<script>
export default {
  name: 'TodoList',
    components: { TodoAdd: () => import('./../components/ToDoAdd.vue')}
}
</script>
<style scoped>
</style>
