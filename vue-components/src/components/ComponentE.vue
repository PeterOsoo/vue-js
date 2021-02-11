<template>
  <h3>Component E</h3>
  <ComponentF />
</template>

<script>
import ComponentF from "./ComponentF";
export default {
  name: "ComponentE",
  components: {
    ComponentF,
  },
};
</script>

<style scoped>
</style>