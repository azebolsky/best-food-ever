<template>
  <form class="add-form">
    <div class="form-control">
      <label>Food</label>
      <!-- v-model binds inputs with data -->
      <input type="text" name="food" v-model="food" placeholder="Add Food" />
    </div>
    <div class="form-control">
      <label>Restaurant</label>
      <!-- v-model binds inputs with data -->
      <input type="text" name="restaurant" v-model="restaurant" placeholder="Add Restaurant" />
    </div>
    <div class="form-control">
      <label>Date Eaten</label>
      <input type="text" name="date" v-model="date" placeholder="Add Day and Time" />
    </div>
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
  name: "AddFood"
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