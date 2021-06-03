<template>
  <header>
    <h1>{{ title }}</h1>
    <Button
      @btn-click="$emit('toggle-add-task')"
      :color="addTaskVisible ? 'red' : 'green'"
      :text="addTaskVisible ? 'Close' : 'Add Task'"
    />
    <!-- <Button color="blue" text="Update task" />
    <Button color="red" text="Delete task" /> -->
  </header>
</template>

<script>
import Button from "./Button";

export default {
  name: "Header",
  props: {
    addTaskVisible: Boolean,
    title: String,
  },
  components: {
    Button,
  },
};
</script>

<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}
</style>