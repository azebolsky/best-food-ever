<template>
  <div class="header">
    <h1>Food Entry</h1>
    <Button
      v-show="homePage"
      @toggle-food="$emit('toggle-food')"
      :showAddFood="showAddFood"
      :text="showAddFood ? 'Close' : 'Add Food'"
      :color="showAddFood ? 'red' : 'blue'"
    />
  </div>
</template>

<script>
import Button from "./Button";

export default {
  name: "Header",
  components: {
    Button,
  },
  props: {
    showAddFood: Boolean,
  },
  computed: {
    homePage() {
      if (this.$route.path === "/") {
        return true;
      } else {
        return false;
      }
    },
  },
};
</script>

<style scoped>
.header {
  display: flex;
  justify-content: space-around;
  align-items: center;
  margin: 10px 0;
}
</style>
