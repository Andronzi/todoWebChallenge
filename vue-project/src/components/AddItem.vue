<template>
  <div>
    <input ref="input" type="text" placeholder="add details" />
    <button @click="add">Add</button>
  </div>
</template>

<script>
export default {
  methods: {
    add() {
      let tasks = JSON.parse(localStorage.getItem("tasks")) || [];
      tasks.push({ id: tasks.length, value: this.$refs.input.value });
      localStorage.setItem("tasks", JSON.stringify(tasks));
      this.$emit("updateTasks", tasks);
    },
  },
};
</script>
