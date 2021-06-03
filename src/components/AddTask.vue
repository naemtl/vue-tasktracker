<template>
  <form @submit="onSubmit" class="add-form">
    <div class="form-control">
      <label>Task</label>
      <input type="text" name="text" placeholder="Add Task" v-model="text" />
    </div>
    <div class="form-control">
      <label>Day & Time</label>
      <input
        type="text"
        name="day"
        placeholder="Add Day &amp; Time"
        v-model="day"
      />
    </div>
    <div class="form-control form-control-check">
      <label>Set Reminder</label>
      <input type="checkbox" name="reminder" v-model="reminder" />
    </div>

    <input type="submit" value="Save Task" class="btn btn-block" />
  </form>
</template>

<script>
export default {
  name: "AddTask",
  data() {
    return {
      day: "",
      reminder: false,
      text: "",
    };
  },
  methods: {
    onSubmit(e) {
      e.preventDefault();
      if (!this.text) {
        alert("You must enter a task description");
        return;
      }
      const newTask = {
        id: Math.floor(Math.random() * 100000),
        text: this.text,
        day: this.day,
        reminder: this.reminder,
      };

      this.$emit("add-task", newTask);

      this.text = "";
      this.day = "";
      this.reminder = false;
    },
  },
};
</script>

<style scoped>
.add-form {
  margin-bottom: 40px;
}
.form-control {
  margin: 20px 0;
}
.form-control label {
  display: block;
}
.form-control input {
  width: 100%;
  height: 40px;
  margin: 5px;
  padding: 3px 7px;
  font-size: 17px;
}
.form-control-check {
  display: flex;
  align-items: center;
}

.form-control-check input {
  height: 20px;
  width: 30px;
}
</style>