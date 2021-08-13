<template>
  <div>
    <form @submit="onSubmit" class="add-form">
      <div class="form-control">
        <label>Task</label>
        <input type="text" v-model="text" name="text" placeholder="Add Task" />
      </div>
      <div class="form-control">
        <label>Day & Time</label>
        <input
          type="text"
          v-model="day"
          name="day"
          placeholder="Add Day & Time"
        />
      </div>
      <div class="form-control form-control-check">
        <label>Set Reminder</label>
        <input type="checkbox" v-model="reminder" name="reminder" />
      </div>

      <input type="submit" value="Save Task" class="btn btn-block" />
    </form>
  </div>
</template>
<script>
export default {
  name: "addTask",
  data() {
    return {
      text: "",
      day: "",
    };
  },
  methods: {
    onSubmit(e) {
      e.preventDefault();
      const newTask = {
        id: Math.floor(Math.random() * 10000),
        text: this.text,
        day: this.day,
      };
      this.text = "";
      this.date = "";
      console.log(newTask);
      this.$emit("add-task", newTask);
    },
  },
};
</script>
<style scope>
.add-form {
  display: flex;
  flex-direction: column;
  gap: 1rem;
}
.form-control label {
  width: 80px;
}
.form-control {
  display: flex;
  justify-content: gap;
  gap: 4rem;
}
.btn {
  width: 200px;
  align-self: center;
}
</style>