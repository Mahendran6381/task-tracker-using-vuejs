<template >
  <AddTask @add-task="addTask" />
  <div class="Tasks">
    <div :key="task.id" v-for="task in tasks" class="Task">
      <Task @delete-task="deleteTask(task.id)" :Task="task" />
    </div>
  </div>
</template>
<script>
import Task from "./Task.vue";
import AddTask from "./addtask.vue";
export default {
  name: "Tasks",
  data() {
    return {
      tasks: [],
    };
  },
  components: {
    Task,
    AddTask,
  },
  methods: {
    deleteTask(id) {
      console.log("Hello I am In methods", id);
      this.tasks = this.tasks.filter((task) => task.id !== id);
    },
    addTask(task) {
      console.log(task);
      this.tasks = [...this.tasks, task];
    },
  },
  created() {
    this.tasks = [
      {
        id: "1",
        text: "Doctors Appointment",
        day: "March 5th at 2:30pm",
        reminder: true,
      },
      {
        id: "2",
        text: "Meeting with boss",
        day: "March 6th at 1:30pm",
        reminder: true,
      },
      {
        id: "3",
        text: "Food shopping",
        day: "March 7th at 2:00pm",
        reminder: false,
      },
    ];
  },
  emits: ["delete-task", "toggle-reminder", "add-task"],
};
</script>
<style scope>
.Task {
  margin: 10px;
  padding: 0rem 1.5rem;
  background: rgba(0, 0, 0, 0.1);
  border-radius: 20px;
}
</style>