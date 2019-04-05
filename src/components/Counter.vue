<template>
  <div>
    <div v-if="!countLoaded">
      <p>Loading...</p>
      </div>
      <div v-else>
    <p>Broj napušavanja do sada: {{ count }}</p>
    <button @click="increment()">Ma puši ga</button>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "HelloWorld",
  data() {
    return {count: 0, countLoaded: false};
  },
  mounted() {
    axios.get("https://api.countapi.xyz/get/pusi.ga/napusavanje").then(response=>{
      this.count = response.data.value;
      this.countLoaded = true;
    });
  },
  methods: {
    increment() {
      this.countLoaded = false;
      axios.get("https://api.countapi.xyz/hit/pusi.ga/napusavanje").then(response=>{
        this.count = response.data.value;
        this.countLoaded = true;
      });
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
