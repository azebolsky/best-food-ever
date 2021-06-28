<template>
  <section class="login-container">
    <form class="login-form">
      <h1>Login</h1>
      <div class="form-control">
        <label>email</label>
        <!-- v-model binds inputs with data -->
        <input type="text" v-model="email" placeholder="name@email.com" />
      </div>
      <div class="form-control">
        <label>password</label>
        <!-- v-model binds inputs with data -->
        <input type="text" v-model="password" placeholder="enter password" />
      </div>
    </form>
    <div @click="$emit('close-login')" class="close-login">
      X
    </div>
  </section>
</template>

<script>
export default {
  name: "Login",
  data() {
    return {
      email: "",
      password: "",
    };
  },
};
</script>

<style scoped>
.login-container {
  width: 100vw;
  height: 100vh;
  position: fixed;
  background: rgba(0, 0, 0, 0.6);
  display: flex;
  align-items: center;
}
.login-form {
  width: 60%;
  height: 80vh;
  margin: 0 auto;
  background: whitesmoke;
}
.login-form h1 {
  margin: 0;
}
.close-login {
  width: 70px;
  height: 70px;
  background: whitesmoke;
  position: absolute;
  top: 0;
  right: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 25px;
  cursor: pointer;
}
</style>
