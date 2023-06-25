<template>
  <div class="tasks">
    <div v-for="task in tasks" :key="task.id">
      <SingleTask
        :task="task"
        @toggleReminder="$emit('toggle-reminder', task.id)"
        @deleteTask="$emit('deleteTask', task.id)"
      />
    </div>
  </div>
</template>

<script>
import SingleTask from "./SingleTask";

export default {
  components: {
    SingleTask,
  },
  name: "Tasks",
  props: {
    tasks: Array,
  },
  emits: ["toggle-reminder", "deleteTask"],
};
</script>

<style>
</style>