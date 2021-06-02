<template>
  <button class="btn" @click="onClick()" :style="{ background: color }">
    {{ text }}
  </button>
</template>

<script>
export default {
  methods: {
    onClick() {
      console.log("You clicked me");
    },
  },
  name: "Button",
  props: {
    color: String,
    text: String,
  },
};
</script>

<style scoped>
</style>