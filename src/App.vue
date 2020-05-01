<template>
  <div id="app">
    <grocery-item v-for="item in groceryList" :key="item" :item="item" />
  </div>
</template>

<script>
import GroceryItem from "./components/GroceryItem.vue";
export default {
  name: "App",
  components: {
    GroceryItem
  },
  data: () => {
    return {
      groceryList: [
        { id: 0, text: "Vegetables" },
        { id: 1, text: "Cheese" },
        { id: 2, text: "Whatever else humans are supposed to eat" }
      ]
    };
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
</style>
