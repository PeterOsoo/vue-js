<template>
  <h1>Props</h1>
  <Greet name="japap" heroName="Super Man" />
  <Greet name="ondiek" heroName="Batman" />
  <Greet name="jaground" heroName="Wonder Man" />
  <Greet :name="name" :heroName="channel" />

  <Article id="title" :likes="50" :isPublished="true" />

  <!-- Provide/ Inject -->
  <h1>Provide/ Inject</h1>
  <h3>App component {{ name }}</h3>
  <ComponentC />
</template>

<script>
import Greet from "./components/Greet.vue";
import Article from "./components/Article.vue";
import ComponentC from "./components/ComponentC.vue";

export default {
  name: "App",
  components: {
    Greet,
    Article,
    ComponentC,
  },
  data() {
    return {
      name: "Jakablak",
      channel: "coding addict",
    };
  },
  provide() {
    return {
      userName: this.name,
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

h1 {
  color: rgb(75, 21, 21);
  padding: 2rem;
}
</style>
