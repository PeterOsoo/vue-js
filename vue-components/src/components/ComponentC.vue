<template>
  <h3>Component C</h3>
  <ComponentE />
</template>

<script>
import ComponentE from "./ComponentE";
export default {
  name: "ComponentC",
  components: {
    ComponentE,
  },
};
</script>

<style scoped>
</style>