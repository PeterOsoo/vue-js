<template>
  <!-- Lifecycle Hooks -->
  <h1>Lifecycle Hooks</h1>
  <Parent />

  <h1>Template Refs</h1>
  <TemplateRef />

  <!-- <h1>Vue HTTP</h1> -->
  <h1>HTTP POST Request</h1>
  <CreatePost />

  <PostList />
</template>

<script>
import PostList from "./components/PostList.vue";
import CreatePost from "./components/CreatePost.vue";
import Parent from "./components/Parent.vue";
import TemplateRef from "./components/TemplateRef.vue";

export default {
  name: "App",
  components: {
    PostList,
    CreatePost,
    Parent,
    TemplateRef,
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
  padding: 1rem 0;
}
</style>
