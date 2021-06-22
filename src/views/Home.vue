<template>
  <div>
    <AddFood v-show="showAddFood" @add-food="addFood" />
    <!-- have to v-bind with : foods because it's dynamic -->
    <Foods @delete-food="deleteFood" :foods="foods" />
  </div>
</template>

<script>
import AddFood from "../components/AddFood";
import Foods from "../components/Foods";

export default {
  name: "Home",
  components: {
    AddFood,
    Foods,
  },
  props: {
    showAddFood: Boolean,
  },
  data() {
    return {
      foods: [],
    };
  },
  methods: {
    async deleteFood(id) {
      // you don't need headers or body
      const res = await fetch(`api/foods/${id}`, {
        method: "DELETE",
      });
      res.status === 200
        ? (this.foods = this.foods.filter((food) => food.id !== id))
        : alert("error deleting task");
    },
    async addFood(newFood) {
      const res = await fetch("api/foods", {
        method: "POST",
        headers: {
          "Content-Type": "application/json",
        },
        body: JSON.stringify(newFood),
      });
      const data = await res.json();
      this.foods = [...this.foods, data];
    },
    // fetch all
    async fetchFoods() {
      const res = await fetch("api/foods");
      const data = await res.json();
      return data;
    },
    async fetchFood(id) {
      const res = await fetch(`api/foods/${id}`);
      const data = await res.json();
      return data;
    },
  },
  // created is a lifecycle method used to load foods when app starts;
  async created() {
    this.foods = await this.fetchFoods();
  },
};
</script>
