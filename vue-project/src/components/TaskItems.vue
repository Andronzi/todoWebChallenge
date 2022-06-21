<template>
  <div class="task-list" v-for="item in tasks" v-bind:key="item.id">
    <input type="checkbox" :id="item.id" @click="toggle">
    <li class="task-list__element">
      {{ item.value }}
    </li>
  </div>
</template>

<script>
export default {
  props: {
    tasks: Array,
  },
  methods: {
    toggle(event) {
      event.target.nextSibling.classList.toggle("line-through");
    }
  }
};
</script>

<style>
  .task-list__element {
    margin-left: 30px;
  }

  .line-through {
    text-decoration: line-through
  }
</style>