<template >
  <div class="task">
    <div>
      <h4>{{ Task.text }}</h4>
      <p>{{ Task.day }}</p>
    </div>
    <i @click="onDelete(Task.id)" class="fa fa-times" aria-hidden="true"></i>
  </div>
</template>
<script>
export default {
  name: "Task",
  props: {
    Task: Object,
  },
  methods: {
    onDelete(id) {
      console.log("HI");
      this.$emit("delete-task", id);
    },
  },
};
</script>
<style scope>
.task {
  display: flex;
  justify-content: space-between;
}
.fa {
  margin-top: 3rem;
  color: red;
}
</style>