<template>
  <h1>Props</h1>
  <Greet name="japap" heroName="Super Man" />
  <Greet name="ondiek" heroName="Batman" />
  <Greet name="jaground" heroName="Wonder Man" />
  <Greet :name="name" :heroName="channel" />

  <Article id="title" :likes="50" :isPublished="true" />
</template>

<script>
import Greet from "./components/Greet.vue";
import Article from "./components/Article.vue";

export default {
  name: "App",
  components: {
    Greet,
    Article,
  },
  data() {
    return {
      name: "Ondiegi",
      channel: "coding addict",
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
