<template>
  <div>{{greet}} {{name}}</div>
  <div v-text="channel"></div>
  <div v-text="detail"></div>
  <div v-html="detail"></div>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      greet: "Hello",
      name: "Rateng",
      channel: "Ondiek",
      detail: "<b> blacklist </b>"
    }
  }  
}
</script>

<style>
#app {
  text-align: center;
}
</style>
