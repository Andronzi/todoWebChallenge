<template>
  <li v-for="item in tasks" v-bind:key="item.id">
    <input type="checkbox">
    {{ item.value }}
  </li>
</template>

<script>
export default {
  props: {
    tasks: Array,
  },
};
</script>
