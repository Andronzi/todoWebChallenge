<template>
  <div class="task-list" v-for="item in tasks" v-bind:key="item.id">
    <input type="checkbox" :id="item.id" @click="toggle($event, item.id)">
    <li v-if="item.status == 'active'" class="task-list__element">
      {{ item.value }}
      {{ item.status }}
    </li>
    <li v-else class="task-list__element completed">
      {{ item.value }}
      {{ item.status }}
    </li>
  </div>
</template>

<script>
export default {
  props: {
    tasks: Array,
  },
  methods: {
    toggle(event, id) {
      event.target.nextSibling.classList.toggle("completed");
      let tasks = JSON.parse(localStorage.getItem("tasks"));
      console.log(id);

      if (tasks[id].status == "active") {
        tasks[id].status = "completed";
      }
      else {
        tasks[id].status = "active";
      }

      localStorage.setItem("tasks", JSON.stringify(tasks));
      this.$emit("updateTasks", tasks);
    }
  }
};
</script>

<style>
  .task-list__element {
    margin-left: 30px;
  }

  .completed {
    text-decoration: line-through
  }
</style>