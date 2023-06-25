<template>
  <div
    tabindex="0"
    :class="[task.reminder ? 'reminderOn' : '', 'singleTask']"
    @dblclick="$emit('toggleReminder')"
  >
    <div class="taskData">
      <div class="title">{{ task.title }}</div>
      <div class="date">{{ task.date }}</div>
    </div>
    <div @click="$emit('deleteTask')" class="close">X</div>
  </div>
</template>

<script>
export default {
  name: "SingleTask",
  props: {
    task: Object,
  },
  emits: ["toggleReminder", "deleteTask"],

  data() {
    let x = "test";

    return {
      title: "MyTitle",
      date: "MyDate",
    };
  },
};
</script>

<style scoped>
.singleTask {
  background: lightgray;
  display: flex;
  justify-content: space-between;
  padding: 20px 10vw 20px 10vw;
  text-align: left;
  margin: 10px;
}

.title {
  font-size: 1.5em;
  font-weight: 500;
  margin-bottom: 5px;
}

.reminderOn {
  border-left: 5px solid green;
}
</style>