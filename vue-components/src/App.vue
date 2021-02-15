<template>
  <h1>Props</h1>
  <Greet name="japap" heroName="Super Man" />
  <Greet name="ondiek" heroName="Batman" />
  <Greet name="jaground" heroName="Wonder Man" />
  <Greet :name="name" :heroName="channel" />

  <Article title="New Article" id="title" :likes="50" :isPublished="true" />

  <!-- Provide/ Inject -->
  <h1>Provide/ Inject</h1>
  <h3>App component {{ name }}</h3>
  <ComponentC />

  <!-- Events -->
  <h1>Component Events</h1>
  <h3>Custom Events</h3>
  <button @click="showPopup = true">Open popup</button>
  <Popup v-show="showPopup" @close="closePopup" />
  <div class="pb">
    <Input v-model="username" />
  </div>

  <!-- Slots -->
  <h1>Slots</h1>
  <!-- <div class="center">
    <Card> </Card>
    <br />
    <Card> Card content </Card>
    <Card> <h2>Card content</h2> </Card>
    <Card> <img src="https://picsum.photos/200" alt="sample" /> </Card>
  </div> -->

  <div class="center pb">
    <Card>
      <template v-slot:header>
        <h3>Header</h3>
      </template>
      <template v-slot:default>
        <img src="https://picsum.photos/200" />
      </template>
      <template v-slot:footer>
        <button>View Details</button>
      </template>
    </Card>
  </div>

  <NameList>
    <template v-slot:default="slotProps">
      {{ slotProps.firstName }} {{ slotProps.lastName }}
    </template>
  </NameList>

  <NameList>
    <template v-slot:default="slotProps">
      {{ slotProps.lastName }}, {{ slotProps.firstName }}
    </template>
  </NameList>

  <!-- Dynamic Components -->
  <br />
  <br />
  <br />
  <button @click="activeTab = 'TabA'">Tab A</button>
  <button @click="activeTab = 'TabB'">Tab B</button>
  <button @click="activeTab = 'TabC'">Tab C</button>

  <!-- <TabA v-if="activeTab === 'TabA'" />
  <TabB v-if="activeTab === 'TabB'" />
  <TabC v-if="activeTab === 'TabC'" /> -->

  <keep-alive>
    <component :is="activeTab"></component>
  </keep-alive>
</template>

<script>
import Greet from "./components/Greet.vue";
import Article from "./components/Article.vue";
import ComponentC from "./components/ComponentC.vue";
import Popup from "./components/Popup.vue";
import Input from "./components/Input.vue";
import Card from "./components/Card.vue";
import NameList from "./components/NameList.vue";
import TabA from "./components/TabA.vue";
import TabB from "./components/TabB.vue";
import TabC from "./components/TabC.vue";

export default {
  name: "App",
  components: {
    Greet,
    Article,
    ComponentC,
    Popup,
    Input,
    Card,
    NameList,
    TabA,
    TabB,
    TabC,
  },
  data() {
    return {
      name: "Jakablak",
      channel: "coding addict",
      showPopup: false,
      username: "",
      activeTab: "TabA",
    };
  },
  methods: {
    closePopup(name) {
      this.showPopup = false;
      console.log("name", name);
    },
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
.center {
  text-align: center;
}

.pb {
  padding: 0.9rem 40%;
}
</style>
