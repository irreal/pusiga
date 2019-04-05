<template>
  <div class="home">
    <img alt="site logo" src="../assets/pusiga-logo.png">
    <h1 class="tagline">Napušavanje počinje uskoro.</h1>
    <counter :count="count" @increment="count+=1"/>
  </div>
</template>


<script>
import Counter from "../components/Counter.vue";
export default {
  components: { Counter },
  name: "home",
  data() {
    return {
      count: 0
    };
  }
};
</script>

<style>
.tagline {
  margin-top: 25px;
}
</style>
