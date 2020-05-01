<template>
  <div>{{ item.text }}</div>
</template>

<script>
export default {
  props: ["item"]
};
</script>


<style scoped>
div {
  margin: 5px;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 8px;
  text-align: left;
}
</style>