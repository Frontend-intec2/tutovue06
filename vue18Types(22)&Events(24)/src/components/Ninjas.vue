<template>
  <div id="ninjas">
    <!--line 6 to be matched with ::    <app-ninjas v-bind:ninjasarray="ninjasarray"></app-ninjas>
    :: in App.vue-->
    <!-- <p>{{ninjasarray}}</p> -->
    <ul>
      <!-- added something in middle of line 6 (next line) -->
      <li
        v-for="ninjaobject in ninjasarray"
        v-bind:key="ninjaobject"
        v-on:click="ninjaobject.show = !ninjaobject.show"
      >
        <h2>{{ ninjaobject.name }}</h2>
        <!-- ninjaobject - ninjasarray; clearer to me -->

        <h3 v-show="ninjaobject.show">{{ ninjaobject.speciality }}</h3>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  // props: ["ninjasarray"],
  // ninjasarray: giving propper names helps with coding, line above, nevertheless here are some validation tricks line below
  props: { ninjasarray: { type: Array, required: true } },

  data() {
    return {};
  }
};
</script>
}
<style scoped>
#ninjas {
  width: 100%;
  max-width: 1200px;
  margin: 40px auto;
  padding: 0 20px;
  box-sizing: border-box;
}

ul {
  display: flex;
  flex-wrap: wrap;
  list-style-type: none;
  padding: 0;
}

li {
  flex-grow: 1;
  flex-basis: 300px;
  text-align: center;
  padding: 0;
  border: 1px solid #222;
  margin: 10px;
}
</style>
