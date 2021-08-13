<template >
  <button @onclick="OnClick()" :style="{ background: color }">Add Task</button>
</template>
<script>
export default {
  name: "Button",
  props: {
    text: String,
    color: String,
  },
  methods: {
    onClick() {
      console.log("HI");
    },
  },
};
</script>
<style scope >
button {
  width: 100px;
  height: 50px;
  background: rgba(0, 0, 0, 0.3);
}
</style>