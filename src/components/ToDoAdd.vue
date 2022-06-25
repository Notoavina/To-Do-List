<template>
  <div class="container">
    <PageTitle label="To do List"></PageTitle>
    <div class="d-flex col-md-12 col-xxl-6 justify-content-center mx-auto mb-5">
        <input type="text" class="form-control border-0 rounded-0" placeholder="Enter a task:" name="task">
        <button class="btn btn-add rounded-0 d-inline-flex align-items-center">
           <i class="bi bi-plus-circle me-2"></i>
            Add Task
        </button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'TodoAdd',
  components: { PageTitle: () => import('./common/PageTitle.vue')}
}
</script>
<style scoped>
.btn-add{
   background: #031955;
   color: #fff;
   min-width: 135px;
}
input, input::placeholder{
    color: #031955;
    font-family: 'Montserrat';
}
</style>
