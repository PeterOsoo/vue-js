<template>
  <div>
    <h4 @mouseover="incrementCount">Hovered {{ count }} times</h4>
  </div>
</template>

<script>
import CounterMixin from "../mixins/counter";

export default {
  name: "HoverCounter",
  mixins: [CounterMixin],
};
</script>

<style scoped>
h4 {
  color: darkslategrey;
}
</style>