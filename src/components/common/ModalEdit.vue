<template>
  <div
    class="modal fade"
    id="exampleModal"
    tabindex="-1"
    aria-labelledby="exampleModalLabel"
    aria-hidden="true"
  >
    <form class="modal-dialog">
      <div class="modal-content">
        <div class="modal-header">
          <h5 class="modal-title" id="exampleModalLabel">Modal title</h5>
          <button
            type="button"
            class="btn-close"
            data-bs-dismiss="modal"
            aria-label="Close"
          ></button>
        </div>
        <div class="modal-body">
          <label for="titleEdit">Title :</label>
          <input
            type="text"
            id="titleEdit"
            class="form-control border-1 rounded-0 col-xxl-12"
            placeholder="Please enter the title of the task here"
            v-model="newtitleValue"
          />
          <label for="descEdit">Description:</label>
          <textarea
            class="form-control col-xxl-12 border-1 rounded-0"
            rows="3"
            id="desc"
            placeholder="Please enter the description of the task here"
            required
            v-model="newDescValue"
          ></textarea>
        </div>
        <div class="modal-footer">
          <button
            type="button"
            class="btn btn-secondary"
            data-bs-dismiss="modal"
          >
            Close
          </button>
          <button type="button" class="btn btn-primary" @click="sendValue()">Save changes</button>
        </div>
      </div>
    </form>
  </div>
</template>

<script>
export default 
{
  name: "ModalEdit",
  props: {
    items: Object
  },
  data: function () {
    return {
      isOpen: false,
      newtitleValue: this.titleValue,
      newDescValue: this.descValue,
    };
  },
  methods:{
    sendValue(){
        this.isOpen = false;
    }
  }
};
</script>
<style scoped>
</style>
