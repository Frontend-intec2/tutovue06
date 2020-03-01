<template>
  <footer>
    <h1>{{copyright}}{{title}}</h1>
  </footer>
</template>

<script>
import { bus } from "../main";
export default {
  props: {
    title: {
      type: String
    }
  },

  data() {
    return { copyright: 'Copyright 2020' }
  },
  created() {
    bus.$on('titleChanged', (data) => {
      this.title = data;
    });
  }
};
</script>