<template>
  <div>{{greet}} {{name}}</div>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      greet: "Hello",
      name: "Rateng"
    }
  }  
}
</script>

<style>
#app {
  text-align: center;
}
</style>
