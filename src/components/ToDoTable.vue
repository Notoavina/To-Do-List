<template>
  <div class="row">
    <ModalEdit :items="getItem"/>
    <div class="col-md-12 col-xxl-12">
      <table class="table bg-light">
        <thead>
          <tr>
            <th scope="col" class="text-center">Title</th>
            <th scope="col" class="text-center">Description</th>
            <th scope="col" class="text-center">Edit</th>
            <th scope="col" class="text-center">Status</th>
            <th scope="col" class="text-center">Delete</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="(listItem, index) in list" :key="index">
            <td class="text-center align-middle">{{ listItem.title }}</td>
            <td class="text-center align-middle">{{ listItem.desc }}</td>
            <td class="text-center align-middle">
              <button type="button" class="btn btn-info rounded-0" data-bs-toggle="modal" data-bs-target="#exampleModal" @click="getIndex(listItem)">
                <i class="bi bi-pencil"></i>
                <span class="d-none d-sm-inline-block">Edit</span>  
              </button>
            </td>
            <td class="text-center align-middle" :id="index" @click="listItem.status = !listItem.status">
              <button class="btn rounded-0" :class="{'btn-success' : listItem.status, 'btn-warning': !listItem.status}">
                <template v-if="listItem.status">
                  <i class="bi bi-check2"></i>
                  <span class="d-none  d-sm-inline-block" >Completed</span>  
                </template>
                <template v-else>
                  <i class="bi bi-patch-exclamation"></i>
                  <span class="d-none  d-sm-inline-block">Uncompleted</span>  
                </template>
              </button>
            </td>
            <td class="text-center align-middle">
              <button class="btn btn-danger rounded-0" :id="index" @click="deleteTask(index)">
                <i class="bi bi-trash"></i>
                <span class="d-none d-sm-inline-block">Delete</span>  
              </button>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
export default {
  name: "ToDoTable",
  props: {
    list: Array,
  },
  components:{
      ModalEdit: () => import("../components/common/ModalEdit.vue")
  },
  methods:{
    deleteTask(indexValue){
      this.$emit('deleteLine', indexValue )
    },
     getItem: function(item){
      return item
    },
  }
};
</script>
<style scoped>
</style>
