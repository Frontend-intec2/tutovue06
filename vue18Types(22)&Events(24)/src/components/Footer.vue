<template>
  <footer>
    <p>{{ copyright }}</p>
    <h1 id="myh1" v-on:mouseover="changeTitle">{{title}}</h1>
  </footer>
</template>

<script>
export default {
  props: {
    title: { type: String }
  },
  data() {
    return { copyright: "Copyright 2020" };
  },
  // delete the method to see the difference
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
footer {
  background: #222;
  padding: 6px;
}

p {
  color: lightgreen;
  text-align: center;
}

#myh1 {
  color: white;
  background: red;
  text-align: center;
}
</style>
