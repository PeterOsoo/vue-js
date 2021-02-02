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

  <!-- array of arrays  -->
  <div v-for="actor in actors" :key="actor.name">
    <h2 class="actor">{{ actor.name }}</h2>
    <p v-for="movie in actor.movies" :key="movie">{{ movie }}</p>
  </div>

  <!-- my info  -->
  <h3 v-for="(value, key, index) in myInfo" :key="value">
    {{ index }} {{ key }} {{ value }}
  </h3>
  <br />
  <template v-for="name in names" :key="name">
    <p>{{ name }}</p>
  </template>

  <!-- conditionally rendering list elements  -->
  <!-- vue evaluates v-if before v-for -->
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

  <!-- Event Handling -->
  <h1>Event Handling</h1>
  <h2>{{ name }}</h2>
  <div>
    <button @click="changeName($event), increment(1, $event)">
      Change name
    </button>
  </div>
  <h2>{{ count }}</h2>
  <div>
    <button @click="increment(1, $event)">Increment</button>
    <button @click="decrement(1)">Decrement</button>
    <button @click="increment(5)">Increment 5</button>
    <button @click="decrement(5)">Decrement 5</button>
  </div>

  <!-- Form Handling -->
  <div>
    <pre>
      {{ JSON.stringify(formValues, null, 2) }}
    </pre>
  </div>
  <form @submit.prevent="submitForm" class="form-data">
    <div>
      <label for="name">Name</label>
      <input type="text" id="name" v-model.trim.lazy="formValues.name" />
    </div>
    <div>
      <label for="profile">Profile Summary</label>
      <textarea id="profile" v-model="formValues.profileSummary" />
    </div>
    <div>
      <label for="country">Country</label>
      <select id="country" v-model="formValues.country">
        <option value="">Select a country</option>
        <option value="kenya">Kenya</option>
        <option value="uganda">Uganda</option>
        <option value="tanzania">Tanzania</option>
      </select>
    </div>
    <div>
      <label for="job-location">Job location</label>
      <select id="job-location" v-model="formValues.jobLocation" multiple>
        <option value="kenya">Kenya</option>
        <option value="uganda">Uganda</option>
        <option value="tanzania">Tanzania</option>
      </select>
    </div>
    <div>
      <input
        id="remoteWork"
        type="checkbox"
        v-model="formValues.remoteWork"
        true-value="yes"
        false-value="no"
      />
      <label for="remoteWork">Open to remote work?</label>
    </div>
    <div>
      <label>Skill set</label>
      <input
        type="checkbox"
        id="html"
        value="html"
        v-model="formValues.skillSet"
      />
      <label for="html">HTML</label>
      <input
        type="checkbox"
        id="css"
        value="css"
        v-model="formValues.skillSet"
      />
      <label for="css">CSS</label>
      <input
        type="checkbox"
        id="javascript"
        value="javascript"
        v-model="formValues.skillSet"
      />
      <label for="javascript">JavaScript</label>
    </div>
    <div>
      <label>Years of Experience</label>
      <input
        type="radio"
        id="0-2"
        value="0-2"
        v-model="formValues.yearsOfExperience"
      />
      <label for="0-2">0-2</label>
      <input
        type="radio"
        id="3-5"
        value="3-5"
        v-model="formValues.yearsOfExperience"
      />
      <label for="3-5">3-5</label>
      <input
        type="radio"
        id="6-10"
        value="6-10"
        v-model="formValues.yearsOfExperience"
      />
      <label for="6-10">5-10</label>
      <input
        type="radio"
        id="10+"
        value="10+"
        v-model="formValues.yearsOfExperience"
      />
      <label for="10+">10+</label>
    </div>
    <div>
      <label for="age">Age</label>
      <input
        @keyup.enter="submitForm"
        type="number"
        id="age"
        v-model.number="formValues.age"
      />
    </div>
    <div>
      <button>Submit</button>
    </div>
  </form>

  <!-- Modifiers  -->
  <h1>Modifiers</h1>
  <p>Trim</p>
  <p>Number</p>
  <p>Lazy - binds on change event and for form validations</p>
  <p>Prevent</p>
  <p>Key</p>
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
      num: 10,
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
      count: 0,
      formValues: {
        name: "",
        profileSummary: "",
        country: "",
        jobLocation: [],
        remoteWork: "no",
        skillSet: [],
        yearsOfExperience: "",
        age: null,
      },
    };
  },
  methods: {
    add(a, b, c) {
      return a + b + c;
    },
    // dont use arrow functions
    multiply(num) {
      return num * this.baseMultiplier;
    },
    increment(num, event) {
      this.count += num;
      console.log(event);
    },
    decrement(num) {
      this.count -= num;
    },
    changeName(event) {
      this.name = "Jakablack";
      console.log("Event", event);
    },
    submitForm() {
      console.log("form values", this.formValues);
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
label {
  font-weight: bold;
  display: flex;
  margin-bottom: 5px;
}
input + label {
  font-weight: bold;
  display: inline-flex;
  margin-right: 20px;
}
input[type="text"],
textarea,
select {
  display: block;
  width: 400px;
  padding: 6px 12px;
  font-size: 14px;
  line-height: 1.42857143;
  color: #555;
  background-color: #fff;
  background-image: none;
  border: 1px solid #ccc;
  border-radius: 4px;
}

.form-data {
  text-align: start;
}
</style>
