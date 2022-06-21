<script setup>
import "./assets/app.css";
import Navbar from "./components/NavComponent.vue";
import Add from "./components/AddItem.vue";
import Tasks from "./components/TaskItems.vue";
</script>

<template>
  <div class="wrapper">
    <h1>#todo</h1>
    <Navbar />
    <Add @updateTasks="tasks = $event" />
    <Tasks :tasks="tasks" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      tasks: JSON.parse(localStorage.getItem("tasks")),
    };
  },
  methods: {
    update() {
      this.tasks = JSON.parse(localStorage.getItem("tasks"));
    },
  },
};
</script>
