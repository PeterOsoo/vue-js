<template>
  <div>
    <h1>Prop Types and Validations</h1>
    <!-- use dollar attribute to bind -->
    <h2 v-bind="$attrs">{{ title }}</h2>
    <h2>Likes - {{ likes }}</h2>
    <h2>Published - {{ isPublished ? "Yes" : "No" }}</h2>
  </div>
</template>

<script>
export default {
  name: "Article",
  props: {
    title: {
      type: String,
      required: true,
      default: "Article default title",
    },
    likes: Number,
    isPublished: {
      type: Boolean,
      required: true,
    },
  },
  //   to ignore default behavior of vue
  inheritAttrs: false,
};
</script>

<style scoped>
</style>