<template>
  <!-- Binding Text -->
  <h1>Binding Text</h1>
  <div>{{ greet }} {{ name }}</div>
  <div v-text="channel"></div>

  <!-- Binding HTML -->
  <h1>Binding HTML</h1>
  <div v-text="detail"></div>
  <div v-html="detail"></div>

  <!-- Binding Attributes -->
  <h1>Binding Attributes</h1>
  <h2 :id="headingId">Heading</h2>
  <button v-bind:disabled="isDisabled">Bind</button>

  <!-- Binding Classes -->
  <h1>Binding Classes</h1>
  <h2 class="underline">Underline</h2>
  <h2 class="underline" v-bind:class="status">Status</h2>

  <!-- <h2 v-bind:class="isPromoted && 'promoted'">Promoted Movie</h2> -->
  <h2 :class="isPromoted && 'promoted'">Promoted Movie</h2>
  <h2 :class="isSoldOut ? 'sold-out' : 'new'">Soldout? Movie</h2>
  <h2 :class="['new', 'promoted']">Newly Promoted Movie</h2>
  <h2 :class="[isPromoted && 'promoted', isSoldOut ? 'sold-out' : 'new']">
    Array Conditional Movie
  </h2>

  <h2
    :class="{
      promoted: isPromoted,
      new: !isSoldOut,
      'sold-out': isSoldOut,
    }"
  >
    Object Conditional Movie
  </h2>

  <!-- Binding Styles -->
  <h1>Binding Styles</h1>
  <h2 :style="headerStyleObject">Style Object</h2>
  <div :style="[baseStyleObject, successStyleObject]">Success Style</div>
  <div :style="[baseStyleObject, dangerStyleObject]">Danger Style</div>

  <br />
  <br />
  <br />
  <br />

  <!-- Conditional Rendering -->
  <h1>Conditional Rendering</h1>
  <h2 v-if="num === 0">The number is zero</h2>
  <h2 v-else-if="num < 0">The number is negative</h2>
  <h2 v-else-if="num > 0">The number is positive</h2>
  <h2 v-else>Not a number</h2>

  <template v-if="showElement">
    <h2>Rateng</h2>
    <h2>Ondiek</h2>
    <h2>Vue 3</h2>
  </template>

  <!-- v show is always available in the DOM even if its false  -->
  <h2 v-show="showElement">Using v-show</h2>

  <!-- List Rendering -->
  <h1>List Rendering</h1>
  <h3 v-for="(name, index) in names" :key="name">{{ index }} {{ name }}</h3>
  <h2 class="underline">Full Names</h2>
  <h3 v-for="name in fullNames" :key="name.first">
    {{ name.first }} {{ name.last }}
  </h3>
  <div v-for="actor in actors" :key="actor.name">
    <h2 class="actor">{{ actor.name }}</h2>
    <p v-for="movie in actor.movies" :key="movie">{{ movie }}</p>
  </div>
  <h2 v-for="(value, key, index) in myInfo" :key="value">
    {{ index }} {{ key }} {{ value }}
  </h2>
  <br />
  <template v-for="name in names" :key="name">
    <p>{{ name }}</p>
  </template>
  <template v-for="name in names" :key="name">
    <h3 v-if="name === 'Clarks'">Wuod {{ name }}</h3>
  </template>

  <!-- Methods -->
  <h1>Methods</h1>
  <h2>{{ 2 + 3 + 5 }}</h2>
  <h2>{{ 5 + 10 + 15 }}</h2>
  <h2>Add method - {{ add(2, 3, 5) }}</h2>
  <h2>Add method - {{ add(5, 10, 15) }}</h2>
  <h2>Multiply method - {{ multiply(10) }}</h2>
  <h2>Multiply method - {{ multiply(baseValue) }}</h2>
</template>

<script>
export default {
  name: "App",
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
      isSoldOut: true,
      highlightColor: "orange",
      headerSize: 50,
      headerStyleObject: {
        color: "orange",
        fontSize: "20px",
        padding: "20px",
      },
      baseStyleObject: {
        fontSize: "20px",
        padding: "10px",
      },
      successStyleObject: {
        color: "green",
        backgroundColor: "lightgreen",
        border: "1px solid green",
      },
      dangerStyleObject: {
        color: "darkred",
        backgroundColor: "red",
        border: "1px solid darkred",
      },
      num: 0,
      showElement: true,
      names: ["Bruce", "Clarks", "Diana"],
      fullNames: [
        { first: "Bruce", last: "Wayne" },
        { first: "Clark", last: "Kent" },
        { first: "Princess", last: "Diana" },
        { first: "Rateng", last: "Japap" },
      ],
      actors: [
        {
          name: "Reymond Reddington",
          movies: ["Blacklist", "American Psycho"],
        },
        {
          name: " Elizabeth Keen",
          movies: ["Titanic", "Inception"],
        },
      ],
      myInfo: {
        name: "Rateng",
        channel: "Ondiek",
        course: "Vue 3",
      },
      baseMultiplier: 5,
      baseValue: 2,
    };
  },
  methods: {
    add(a, b, c) {
      return a + b + c;
    },
    multiply(num) {
      return num * this.baseMultiplier;
    },
  },
};
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

.actor {
  color: darkblue;
}
</style>
