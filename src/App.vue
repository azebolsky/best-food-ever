<template>
  <div class="container">
    <Header @btn-click="$emit()" />
    <AddFood />
    <!-- have to v-bind with : foods because it's dynamic -->
    <Foods @delete-food="deleteFood" :foods="foods" />
  </div>
</template>

<script>
import Header from "./components/Header";
import Foods from "./components/Foods";
import AddFood from "./components/AddFood";

export default {
  name: "App",
  components: {
    Header,
    Foods,
    AddFood
  },
  data() {
    return {
      foods: []
    };
  },
  methods: {
    deleteFood(id) {
      // console.log(id);
      this.foods = this.foods.filter(food => food.id !== id);
    }
  },
  // created is a lifecycle method used to load foods when app starts;
  created() {
    this.foods = [
      {
        id: 1,
        rank: 3,
        foodType: "sandwich",
        food: "Au Jus Sandwich",
        restaurant: "Rebel Cheese",
        date: "June 8th, 2021"
      },
      {
        id: 2,
        rank: 1,
        foodType: "sandwich",
        food: "Al Pastor Torta",
        restaurant: "Nunos",
        date: "March 8th, 2020"
      },
      {
        id: 3,
        rank: 2,
        foodType: "sandwich",
        food: "Pesto Sandwich",
        restaurant: "Bar None",
        date: "June 8th, 2021"
      }
    ];
  }
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.container {
  width: 70%;
  height: 100%;
  margin: 0 auto;
  padding: 10px;
  border-radius: 5px;
  border: 2px solid gray;
}
</style>
