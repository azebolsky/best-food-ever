<template>
  <section class="login-container">
    <form class="login-form">
      <div class="inner-container">
        <span class="header">
          <h3>Sign in to continue</h3>
          <h3 class="login-header">
            Not registered?
            <p @click="$emit('register-toggle')">Register here</p>
          </h3>
        </span>
        <div class="form-control">
          <!-- v-model binds inputs with data -->
          <input type="text" v-model="email" placeholder="email" />
        </div>
        <div class="form-control">
          <!-- v-model binds inputs with data -->
          <input type="text" v-model="password" placeholder="password" />
        </div>
        <input type="submit" value="Login Now" class="btn" />
      </div>
    </form>
    <div @click="$emit('close-login')" class="close-login">
      X
    </div>
  </section>
</template>

<script>
export default {
  name: "Register",
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
  width: 600px;
  height: 55vh;
  margin: 0 auto;
  background: whitesmoke;
}
.inner-container {
  width: 80%;
  height: 90%;
  margin: 50px auto;
}
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}
.header h3 {
  font-size: 20px;
  margin: 0;
}
.login-header {
  font-weight: 400;
  display: flex;
}
.inner-container p {
  margin-left: 3px !important;
  margin: 0;
  color: rgb(62, 187, 167);
  font-weight: 600;
  cursor: pointer;
}
.inner-container p:hover {
  color: rgb(42, 125, 111);
}
.form-control {
  width: 100%;
}
.form-control input {
  width: 98%;
  height: 50px;
  font-size: 20px;
  margin: 10px 0;
  padding: 0 0 0 10px;
  border: 1px solid gray;
}
.btn {
  width: 100%;
  height: 50px;
  background: rgb(62, 187, 167);
  cursor: pointer;
  color: whitesmoke;
  font-size: 20px;
  border: none;
  margin-top: 20px;
}
.btn:hover {
  background: rgb(42, 125, 111);
  transition: 0.5s;
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
.close-login:hover {
  opacity: 0.8;
  transition: 0.5s;
}
</style>
