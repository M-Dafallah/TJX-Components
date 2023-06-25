<template>
  <div class="addTask">
    <form @submit="onSubmit">
      <div class="inputTask">
        <label for="task">Task</label>
        <input name="task" type="text" v-model="task.title" />
      </div>

      <div class="inputDate">
        <label for="date">Date</label>
        <input name="date" type="text" v-model="task.date" />
      </div>

      <div class="inputReminder">
        <label for="reminder">Reminder</label>
        <input name="reminder" type="checkbox" v-model="task.reminder" />
      </div>

      <button class="btn">Save Task</button>
    </form>
  </div>
</template>

<script>
export default {
  name: "AddTask",
  emits: ["sumbitTask"],
  data() {
    let task = {
      id: Math.floor(Math.random() * 1000),
      title: "",
      date: "",
      reminder: false,
    };

    return {
      task,
    };
  },

  methods: {
    onSubmit(e) {
      e.preventDefault();
      this.$emit("submitTask", this.task);
    },
  },
};
</script>

<style scoped>
.addTask {
  border: 1px solid black;
  margin: 0 10vw 0 10vw;
  padding: 10px 0 10px 0;
}

.inputTask,
.inputDate {
  display: flex;
  flex-direction: column;
  margin-left: 20vw;
  margin-right: 20vw;
  margin-bottom: 10px;
}

.inputTask label,
.inputDate label {
  align-self: flex-start;
  font-size: 1.5em;
}

.inputReminder {
  margin-bottom: 10px;
  align-self: flex-start;
}

.btn {
  background: black;
  color: white;
  padding-top: 5px;
  padding-bottom: 5px;
  padding-top: 10px;
  padding-left: 70px;
  padding-right: 70px;
}
</style>