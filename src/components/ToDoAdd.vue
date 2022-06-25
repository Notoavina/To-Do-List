<template>
  <div class="row">
    <PageTitle label="To do List"></PageTitle>
    <form class="col-md-12 col-xxl-12 mb-3 w-100">
      <div>
        <div class="h5 mb-3 text-danger p-0">
          Number of non completed task:
          <span class="text-warning"> {{ undone }}</span>
        </div>
        <div class="mb-2 p-0">
          <label for="title " class="mb-1">Title:</label>
          <input
            type="text"
            class="form-control border-1 rounded-0 col-xxl-12"
            placeholder="Please enter the title of the task here"
            name="task"
            id="title"
            required
            v-model="titleValue"
          />
        </div>
        <div class="mb-2 p-0">
          <label for="desc" class="mb-1"> Description: </label>
          <textarea
            class="form-control col-xxl-12 border-1 rounded-0"
            rows="3"
            id="desc"
            placeholder="Please enter the description of the task here"
            required
            v-model="descValue"
          ></textarea>
        </div>
        <button
          class="
            btn btn-add
            rounded-0
            d-inline-flex
            align-items-center
            justify-content-center
            w-100
          "
          type="submit"
          @click.prevent="updateList()"
        >
          <i class="bi bi-plus-circle me-2"></i>
          Add Task
        </button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: "TodoAdd",
  props: {
    undone: Number,
  },
  components: { PageTitle: () => import("./common/PageTitle.vue") },
  data: function () {
    return {
      titleValue: null,
      descValue: null,
      status: false
    };
  },
  methods: {
    updateList() {
      if (this.titleValue != null && this.descValue != null) {
        this.$emit("updateList", {
          title: this.titleValue,
          desc: this.descValue,
          status: this.status,
        });
        this.titleValue = "";
        this.descValue = "";
      }
    },
  },
};
</script>
<style scoped>
label {
  color: #fff;
}
.btn-add {
  background: #031955;
  color: #fff;
  min-width: 135px;
  font-weight: 600;
}
label {
  font-size: 16px;
}
input,
input::placeholder,
textarea,
textarea::placeholder {
  color: #031955;
  font-size: 14px;
  font-family: "Montserrat";
}
</style>
