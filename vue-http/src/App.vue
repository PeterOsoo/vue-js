<template>
  <!-- Lifecycle Hooks -->
  <h1>Lifecycle Hooks</h1>
  <Parent />

  <!-- <h1>Vue HTTP</h1> -->
  <h2>HTTP POST Request</h2>
  <CreatePost />

  <PostList />
</template>

<script>
import PostList from "./components/PostList.vue";
import CreatePost from "./components/CreatePost.vue";
import Parent from "./components/Parent.vue";

export default {
  name: "App",
  components: {
    PostList,
    CreatePost,
    Parent,
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
