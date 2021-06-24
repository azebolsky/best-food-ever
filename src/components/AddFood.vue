<template>
  <form @submit="onSubmit" class="add-form">
    <div class="form-control">
      <label>Food</label>
      <!-- v-model binds inputs with data -->
      <input type="text" name="food" v-model="food" placeholder="Add Food" />
    </div>
    <div class="form-control">
      <label>Restaurant</label>
      <!-- v-model binds inputs with data -->
      <input
        type="text"
        name="restaurant"
        v-model="restaurant"
        placeholder="Add Restaurant"
      />
    </div>
    <div class="form-control">
      <label>Date Eaten</label>
      <input
        type="text"
        name="date"
        v-model="date"
        placeholder="Add Day and Time"
      />
    </div>
    <section class="veg-section">
      <div class="form-control-check">
        <label>Vegan</label>
        <input
          type="checkbox"
          name="vegan"
          v-model="vegan"
          v-if="!vegetarian"
        />
      </div>
      <div class="form-control-check">
        <label>Vegetarian</label>
        <input
          type="checkbox"
          name="vegetarian"
          v-model="vegetarian"
          v-if="!vegan"
        />
      </div>
    </section>
    <div class="form-control">
      <label>Rank</label>
      <select name="rank" v-model="rank">
        <option value="1">1</option>
        <option value="2">2</option>
        <option value="3">3</option>
        <option value="4">4</option>
      </select>
    </div>
    <input type="submit" value="Save Task" class="btn btn-block" />
  </form>
</template>

<script>
export default {
  name: "AddFood",
  data() {
    return {
      food: "",
      restaurant: "",
      date: "",
      rank: "",
      vegan: false,
      vegetarian: false,
    };
  },
  methods: {
    onSubmit(e) {
      e.preventDefault();
      if (!this.food) {
        alert("please add a food");
        return;
      }
      const newFood = {
        // id: Math.floor(Math.random() * 100000),
        food: this.food,
        restaurant: this.restaurant,
        date: this.date,
        rank: this.rank,
        vegan: this.vegan,
        vegetarian: this.vegetarian,
      };
      this.$emit("add-food", newFood), (this.food = "");
      this.restaurant = "";
      this.date = "";
      this.rank = "";
      this.vegan = false;
      this.vegetarian = false;
    },
  },
};
</script>

<style scoped>
.add-form {
  margin-bottom: 40px;
}
.form-control {
  margin: 5px 0;
}
.form-control label {
  display: block;
}
.form-control input {
  width: 80%;
  height: 30px;
  margin: 5px;
  padding: 3px 7px;
  font-size: 17px;
}
.veg-section {
  display: flex;
  justify-content: space-evenly;
}
.form-control-check {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.form-control-check label {
  flex: 1;
}
.form-control-check input {
  flex: 2;
  height: 20px;
}
</style>
