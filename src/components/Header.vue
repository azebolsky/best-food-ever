<template>
  <div class="header">
    <h1>Food Entry</h1>
    <Button
      @toggle-food="$emit('toggle-food')"
      :showAddFood="showAddFood"
      text="Add Food"
      color="blue"
    />
  </div>
</template>

<script>
import Button from "./Button";

export default {
  name: "Header",
  components: {
    Button
  },
  props: {
    showAddFood: Boolean
  }
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