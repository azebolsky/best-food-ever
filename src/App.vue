<template>
  <div class="container">
    <Header
      @toggle-food="toggleFoodButton"
      :showAddFood="showAddFood"
      @btn-click="$emit()"
    />
    <router-view :showAddFood="showAddFood"></router-view>
    <Footer />
  </div>
</template>

<script>
import Header from "./components/Header";
import Footer from "./components/Footer";

export default {
  name: "App",
  components: {
    Header,
    Footer,
  },
  data() {
    return {
      showAddFood: false,
    };
  },
  methods: {
    toggleFoodButton() {
      this.showAddFood = !this.showAddFood;
    },
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

.container {
  width: 70%;
  height: 100%;
  margin: 0 auto;
  padding: 10px;
  border-radius: 5px;
  border: 2px solid gray;
}
</style>
