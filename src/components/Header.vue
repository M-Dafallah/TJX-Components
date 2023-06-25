<template>
  <div class="header">
    <div class="title">Task Tracker</div>

    <button @click="$emit('toggleAddTask')" class="btn">
      {{ showAddTask ? "Hide" : "Add Task" }}
    </button>
  </div>
</template>

<script>
export default {
  name: "Header",
  emits: ["toggleAddTask"],
  props: ["showAddTask"],
};
</script>

<style scoped>
.header {
  display: flex;
  justify-content: space-between;
  padding-left: 10vw;
  padding-right: 10vw;
  padding-top: 30px;
  padding-bottom: 25px;
}
.header .title {
  font-size: 50px;
}

.btn {
  background: green;
  align-self: center;
  padding: 15px;
  color: white;
  font-size: 20px;
}
</style>