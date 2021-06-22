<template>
  <section>
    <div :key="food.id" v-for="food in foods">
      <Food @delete-food="$emit('delete-food', food.id)" :food="food" />
    </div>
  </section>
</template>

<script>
import Food from "./Food";

export default {
  name: "Foods",
  props: {
    foods: Array
  },
  components: {
    Food
  }
};
</script>