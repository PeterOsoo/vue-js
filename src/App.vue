<template>
  <div>{{greet}} {{name}}</div>
  <div v-text="channel"></div>

  <div v-text="detail"></div>
  <div v-html="detail"></div>

  <h2 v-bind:id="headingId">Heading</h2>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      greet: "Hello",
      name: "Rateng",
      channel: "Ondiek",
      detail: "<b> blacklist </b>",
      headingId: "Heading"
    }
  }  
}
</script>

<style>
#app {
  text-align: center;
}
</style>
