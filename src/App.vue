<template>
  <div>
    <div v-if="showLogReg">
      <Login @close-login="closeLogin" />
    </div>
    <NavBar @show-login-reg="showLoginReg" />
    <div class="container">
      <Header
        @toggle-food="toggleFoodButton"
        :showAddFood="showAddFood"
        @btn-click="$emit()"
      />
      <router-view :showAddFood="showAddFood"></router-view>
      <Footer />
    </div>
  </div>
</template>

<script>
import Header from "./components/Header";
import Footer from "./components/Footer";
import NavBar from "./components/NavBar";
import Login from "./components/Login";

export default {
  name: "App",
  components: {
    Header,
    Footer,
    NavBar,
    Login,
  },
  data() {
    return {
      showAddFood: false,
      showLogReg: false,
    };
  },
  methods: {
    toggleFoodButton() {
      this.showAddFood = !this.showAddFood;
    },
    showLoginReg() {
      this.showLogReg = !this.showLogReg;
    },
    closeLogin() {
      this.showLogReg = !this.showLogReg;
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
  box-sizing: border-box;
  margin: 0;
}

body {
  margin: 0;
  background: whitesmoke;
}

.container {
  width: 70%;
  height: 100%;
  margin: 0 auto;
  padding: 10px;
  border-radius: 5px;
  border: 2px solid #c9c9c9;
}
</style>
