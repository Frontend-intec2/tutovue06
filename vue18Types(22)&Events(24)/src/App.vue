<template>
  <div id="App">
    <!-- limegreen belongs to #24 -->
    <app-header v-bind:title="title" v-on:changeTitle="updateTitle($event)"></app-header>
    <app-ninjas v-bind:ninjasarray="ninjasarray"></app-ninjas>
    <!-- this is the event -->
    <app-footer v-bind:title="title" v-on:changeTitle="updateTitle($event)"></app-footer>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Ninjas from "./components/Ninjas.vue";
import Footer from "./components/Footer.vue";

export default {
  components: {
    "app-header": Header,
    "app-footer": Footer,
    "app-ninjas": Ninjas
  },
  data() {
    return {
      ninjasarray: [
        { name: "Manu", speciality: "kind1", show: false },
        { name: "Mounir", speciality: "kind2", show: false },
        { name: "Salai", speciality: "kind3", show: false },
        { name: "Mihai", speciality: "kind4", show: false },
        { name: "Kenneth", speciality: "kind5", show: false },
        { name: "Denis", speciality: "kind6", show: false }
      ],
      title: "Vue1 Ninjas"
    };
  },
  methods: {
    updateTitle: function(updatedTitle) {
      this.title = updatedTitle;
    }
  }
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
