<template>
  <button @click="handleClick" :style="{ background: color }" class="btn">
    {{ text }}
  </button>
</template>

<script>
export default {
  name: "Button",
  props: ["text", "color"],
  methods: {
    handleClick() {
      console.log("Hello");
    },
  },
};
</script>

<style>
</style>