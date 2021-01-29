<template>
  <div>{{greet}} {{name}}</div>
  <div v-text="channel"></div>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      greet: "Hello",
      name: "Rateng",
      channel: "Ondiek"
    }
  }  
}
</script>

<style>
#app {
  text-align: center;
}
</style>
