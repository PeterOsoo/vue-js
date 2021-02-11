<template>
  <div>
    <h3>this is popup</h3>
    <button @click="$emit('close', 'Rateng')">close popup</button>
  </div>
</template>

<script>
export default {
  name: "Popup",
  emits: ["close"],
};
</script>

<style  scoped>
</style>