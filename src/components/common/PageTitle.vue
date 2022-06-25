<template>
    <div class="my-5 text-center">
       <h1 class="h1"> {{ label }}</h1>
    </div>
</template>

<script>
export default {
  name: 'PageTitle',
  props:  {
    label: String,
  }
}
</script>
<style scoped>
h1{
  color: #fff;
}
</style>
