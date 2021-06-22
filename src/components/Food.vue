<template>
  <section class="food-container">
    <div class="rank">{{food.rank}}</div>
    <span class="food-content">
      <div class="food">{{food.food}}</div>
      <div>{{food.restaurant}}</div>
    </span>
    <i @click="$emit('delete-food', food.id)" class="fas fa-times"></i>
  </section>
</template>

<script>
export default {
  name: "Food",
  props: {
    food: Object
  }
};
</script>

<style scoped>
.food-container {
  width: 80%;
  height: 100%;
  margin: 5px auto;
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
  background-color: aliceblue;
}
.food-content {
  text-align: left;
  width: 60%;
}
.rank {
  margin-left: 15px;
  font-size: 20px;
}
.food {
  font-size: 20px;
  font-weight: bold;
}
.fas {
  color: red;
  margin-right: 20px;
}
</style>