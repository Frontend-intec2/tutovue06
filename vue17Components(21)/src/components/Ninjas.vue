<template>
  <div id="ninjas">
    <ul>
      <!-- added something in middle of line 4 (next line) -->
      <li
        v-for="ninjaobject in ninjasarray"
        v-bind:key="ninjaobject"
        v-on:click="ninjaobject.show = !ninjaobject.show"
      >
        <!-- added son line 7 to avoid a warning -->

        <h2>{{ ninjaobject.name }}</h2>
        <!-- ninjaobject - ninjasarray; clearer to me -->

        <h3 v-show="ninjaobject.show">{{ ninjaobject.speciality }}</h3>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      ninjasarray: [
        { name: "Manu", speciality: "kind1", show: false },
        { name: "Mounir", speciality: "kind2", show: false },
        { name: "Salai", speciality: "kind3", show: false },
        { name: "Mihai", speciality: "kind4", show: false },
        { name: "Kenneth", speciality: "kind5", show: false },
        { name: "Denis", speciality: "kind6", show: false }
      ]
    };
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
