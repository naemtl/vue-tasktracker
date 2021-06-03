<template>
  <div v-for="task in tasks" :key="task.id">
    <Task
      @delete-task="$emit('delete-task', task.id)"
      @toggle-reminder="$emit('toggle-reminder', task.id)"
      :task="task"
    />
  </div>
</template>

<script>
import Task from "./Task";
export default {
  name: "Tasks", // name of component
  props: {
    tasks: Array,
  },
  components: {
    // child components
    Task,
  },
  emits: ["delete-task", "toggle-reminder"],
};
</script>

<style scoped>
</style>