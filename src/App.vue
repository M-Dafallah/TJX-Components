<template>
  <div id="app">
    <h1>Pre-Ticket Prep Work</h1>
    <div v-show="false">
      <Header
        tabindex="0"
        @toggleAddTask="toggleAddtaskModule"
        :showAddTask="showAddTask"
      />
      <AddTask v-if="showAddTask" @submitTask="submitTask" />
      <Tasks
        :tasks="tasks"
        tabindex="0"
        @toggle-reminder="toggleReminder"
        @deleteTask="deleteTask"
      />
    </div>

    <LoginMain />
  </div>
</template>

<script>
import HelloWorld from "./components/HelloWorld.vue";
import Header from "./components/Header";
import Tasks from "./components/Tasks";
import LoginMain from "./components/Login-Component/LoginMain";

import AddTask from "./components/AddTask";
export default {
  name: "App",
  components: {
    HelloWorld,
    Header,
    AddTask,
    Tasks,
    LoginMain,
  },
  data() {
    let showAddTask = false;
    let tasks = [
      {
        id: 1,
        title: "Task 1",
        date: "5 July 2023",
        reminder: false,
      },
      {
        id: 2,
        title: "Task 2",
        date: "1 Jan 2023",
        reminder: true,
      },
      {
        id: 3,
        title: "Task 3",
        date: "6 March 2023",
        reminder: false,
      },
    ];

    return {
      tasks,
      showAddTask,
    };
  },

  methods: {
    toggleReminder(id) {
      this.tasks = this.tasks.map((task) =>
        task.id === id ? { ...task, reminder: !task.reminder } : task
      );
    },

    submitTask(task) {
      console.log(task);
      this.tasks = [...this.tasks, task];
    },

    deleteTask(id) {
      this.tasks = this.tasks.filter((task) => task.id !== id);
    },
    toggleAddtaskModule() {
      this.showAddTask = !this.showAddTask;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  margin-left: 5vw;
  margin-right: 5vw;

  border: 1px solid black;
}
</style>
