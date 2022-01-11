<template >
  <header>
    <h1>Task Tracker</h1>
    <h1>{{ title }}</h1>
    <Button text="Add Task" color="green" />
  </header>
</template>
<script>
import Button from "./Button";

export default {
  name: "Header",
  props: ["title"],
  components: { Button },
};
</script>
<style scoped>
header {
  display: plex;
  justify-content: space-between;
  align-items: center;
  margin: bottom;
}
</style>

