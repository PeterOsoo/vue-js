<template>
  <!-- Binding Text -->
  <h1>Binding Text</h1>
  <div>{{greet}} {{name}}</div>
  <div v-text="channel"></div>

  <!-- Binding HTML -->
  <h1>Binding HTML</h1>
  <div v-text="detail"></div>
  <div v-html="detail"></div>

  <!-- Binding Attributes -->
  <h1>Binding Attributes</h1>
  <h2 v-bind:id="headingId">Heading</h2>
  <button v-bind:disabled="isDisabled">Bind</button>

  <!-- Binding Classes -->
  <h1>Binding Classes</h1>
  <h2 class="underline">Underline</h2>
  <h2 class="underline" v-bind:class="status">Status</h2>

  <h2 v-bind:class="isPromoted && 'promoted'">Promoted Movie</h2>
  <h2 v-bind:class="isSoldOut ? 'sold-out' : 'new'">Soldout? Movie</h2>
  <h2 v-bind:class="['new', 'promoted']">Newly Promoted Movie</h2>
  <h2 v-bind:class="[isPromoted && 'promoted', isSoldOut ? 'sold-out' : 'new']">
    Array Conditional Movie
  </h2>

   <h2
    v-bind:class="{
      promoted: isPromoted,
      new: !isSoldOut,
      'sold-out': isSoldOut,
    }"
  >
    Object Conditional Movie
  </h2>

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
      headingId: "Heading",
      isDisabled: true,
      status: "success",
      isPromoted: true,
      isSoldOut: true
    }
  }  
}
</script>

<style>
#app {
  text-align: center;
}

h1 {
  color: darkblue;
}

.underline {
  text-decoration: underline;
}

.promoted {
  font-style: italic;
}
.sold-out {
  color: red;
}
.new {
  color: olivedrab;
}
</style>
