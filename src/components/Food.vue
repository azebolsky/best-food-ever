<template>
  <section class="food-container">
    <div class="rank">{{ food.rank }}</div>
    <span class="food-content">
      <div class="food">{{ food.food }}</div>
      <div>{{ food.restaurant }}</div>
    </span>
    <p v-if="food.vegan" class="veg">vegan</p>
    <p v-if="food.vegetarian" class="veg">vegetarian</p>
    <i @click="$emit('delete-food', food.id)" class="fas fa-times"></i>
  </section>
</template>

<script>
export default {
  name: "Food",
  props: {
    food: Object,
  },
};
</script>

<style scoped>
.food-container {
  width: 85%;
  height: 100%;
  margin: 5px auto;
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
  background-color: aliceblue;
}
.food-content {
  width: 40%;
}
.food-content div {
  text-align: left;
}
.rank {
  margin-left: 15px;
  font-size: 20px;
}
.food {
  font-size: 20px;
  font-weight: bold;
}
.veg {
  padding: 5px;
  background: green;
  color: white;
  border-radius: 5px;
  text-align: center;
  width: 80px;
}
.fas {
  color: red;
  margin-right: 20px;
  max-width: 30px;
  cursor: pointer;
}
</style>
