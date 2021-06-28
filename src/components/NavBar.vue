<template>
  <section class="nav-container">
    <div class="menu">
      <i class="fas fa-bars"></i>
      <h1>Menu</h1>
    </div>
    <div class="title">
      <i class="fas fa-pizza-slice"></i>
      <h1>Best Food I've Ever</h1>
    </div>
    <div @click="$emit('toggle-login')" class="login-reg">
      Login / Register
    </div>
  </section>
</template>

<script>
export default {
  name: "NavBar",
};
</script>

<style scoped>
.nav-container {
  width: 100%;
  height: 70px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
  border-bottom: 1px solid #c9c9c9;
}
.title,
.menu {
  display: flex;
  align-items: center;
}
.menu {
  height: 100%;
  margin-left: 15px;
  padding-right: 10px;
  border-right: 1px solid #c9c9c9;
  cursor: pointer;
}
.menu:hover {
  color: #567594;
}
.login-reg {
  display: flex;
  align-items: center;
  height: 100%;
  margin-right: 15px;
  padding-left: 10px;
  border-left: 1px solid #c9c9c9;
  cursor: pointer;
}
.login-reg:hover {
  color: #567594;
}
h1 {
  margin: 0 10px;
}
.fas {
  font-size: 20px;
}
</style>
