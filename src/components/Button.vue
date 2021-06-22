<template>
  <div>
    <!-- @click is short for v-on:click -->
    <button @click="onClick()" class="btn" :style="{background: color}">{{text}}</button>
  </div>
</template>

<script>
export default {
  name: "Button",
  props: {
    text: String,
    color: String,
    showAddFood: Boolean
  },
  methods: {
    onClick() {
      this.$emit("toggle-food");
    }
  }
};
</script>

<style scoped>
.btn {
  width: 100px;
  height: 50px;
  border: none;
  border-radius: 5px;
  color: white;
  font-size: 18px;
  cursor: pointer;
  margin-bottom: 10px;
}
</style>