<template>
  <div>
    <div class="fade" v-if="showLogin">
      <Login @close-login="closeLogin" @register-toggle="registerToggle" />
    </div>
    <div class="fade" v-if="showRegister">
      <Register @close-login="closeLogin" />
    </div>
    <NavBar @toggle-login="toggleLogin" />
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
import Register from "./components/Register";

export default {
  name: "App",
  components: {
    Header,
    Footer,
    NavBar,
    Login,
    Register,
  },
  data() {
    return {
      showAddFood: false,
      showLogin: false,
      showRegister: false,
    };
  },
  methods: {
    toggleFoodButton() {
      this.showAddFood = !this.showAddFood;
    },
    toggleLogin() {
      this.showLogin = !this.showLogin;
    },
    closeLogin() {
      this.showLogin = this.showLogin ? !this.showLogin : "";
      this.showRegister = this.showRegister ? !this.showRegister : "";
    },
    registerToggle() {
      console.log("hey");
      this.showLogin = !this.showLogin;
      this.showRegister = !this.showRegister;
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

.fade {
  transition: 0.5s;
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
