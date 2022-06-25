<template>
  <div class="container">
    <TodoAdd :undone="getStatus" v-on:updateList="addTask($event)" />
    <div class="bg-danger text-warning text-center p-2 mb-3" v-if="error">
      Field title or description must be fill
    </div>
    <ToDoTable :list="taskList" v-on:deleteLine="deleteLine($event)" />
  </div>
</template>

<script>
export default {
  name: "TodoList",
  components: {
    TodoAdd: () => import("./../components/ToDoAdd.vue"),
    ToDoTable: () => import("../components/ToDoTable.vue"),
  },
  data: function () {
    return {
      taskList: [
        {
          title: "Asus",
          desc: "Lorem Ipsum is simply dummy text of the printing and typesetting industry. ",
          status: true,
        },
        {
          title: "HP",
          desc: "Lorem Ipsum is simply dummy text of the printing and typesetting industry. ",
          status: false,
        },
        {
          title: "Acer",
          desc: "Lorem Ipsum is simply dummy text of the printing and typesetting industry.",
          status: false,
        },
      ],
      error: false,
    };
  },
  computed: {
    getStatus: function () {
      return this.taskList.filter((item) => item.status == false).length;
    },
  },
  methods: {
    addTask(item) {
      this.error = false;
      this.taskList.push(item);
    },
    deleteLine(index) {
      this.taskList.splice(index, 1);
    },
  },
};
</script>
<style scoped>
</style>
