<template>
  <footer>
    <p>Copyright &copy; 2021</p>
    <router-link to="/about">About</router-link>
  </footer>
</template>

<script>
export default {
  name: "Footer",
};
</script>

<style scoped>
a {
  color: darkgrey;
}
footer {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-content: center;
}
</style>
