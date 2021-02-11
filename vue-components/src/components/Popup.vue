<template>
  <div>
    <h3>this is popup</h3>
    <input type="text" v-model="name" />
    <button @click="$emit('close', name)">close popup</button>
  </div>
</template>

<script>
export default {
  name: "Popup",
  data() {
    return {
      name: "",
    };
  },
  emits: ["close"],
};
</script>

<style  scoped>
</style>