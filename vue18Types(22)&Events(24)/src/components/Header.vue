<template>
  <header>
    <!-- lesson 24 changing the value of strings with GLOBAL EVENTS -->
    <h1 v-on:click="changeTitle">{{title}}</h1>
  </header>
</template>

<script>
export default {
  // validation added for lesson 24
  props: {
    title: { type: String }
  },
  data() {
    // return { title: "Vue Ninjas" };
    // title is given in App.vue line 31
  },
  methods: {
    /* lesson 24 changing the value of strings with GLOBAL EVENTS */
    changeTitle: function() {
      this.$emit("changeTitle", "Vue Wizards");
    }
  }
};
</script>
}
<style scoped>
header {
  background: lime;
  padding: 10px;
}
h1 {
  color: #222;
  text-align: center;
}
</style>
