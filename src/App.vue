<template>
  <div id="app">
    <my-component :label="labelA" @update="statea= $event"/>
    <div>X</div>
    <my-component :label="labelB" @update="stateb= $event"/>
    <div>=</div>
    <my-result>{{result}}</my-result>
  </div>
</template>

<script>
import MyComponent from "./components/MyComponent.vue";
import MyResult from "./components/MyResult.vue";

export default {
  name: "app",
  components: {
    MyComponent,
    MyResult
  },
  data() {
    return {
      available: 100,
      items: [],
      labelA: "A",
      labelB: "B",
      statea: 0,
      stateb: 0
    };
  },
  computed: {
    result() {
      return this.statea * this.stateb;
    }
  },
  created() {
    this.fetchItems();
  }
};
</script>

<style lang="scss">
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  font-size: 36px;
  display: flex;
  justify-content: center;
  align-items: center;
  & > div + div {
    margin-left: 30px;
  }

  .counter {
    margin-bottom: 1em;
  }
}
</style>
