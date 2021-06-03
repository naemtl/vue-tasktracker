<template>
  <button class="btn" @click="onClick()" :style="{ background: color }">
    {{ text }}
  </button>
</template>

<script>
export default {
  methods: {
    onClick() {
      this.$emit("btn-click");
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