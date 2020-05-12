
<template>
  <div>
    <button @click.stop="add(2)">
      add
    </button>

    <input :value="counter" @keyup.up="add(1)" @keyup.down="add(-1)">

    <p>
      Counter: {{ counter }}
    </p>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      counter: 0,
    }
  },

  methods: {
    add(number = 1) {
      this.counter += number;
    }
  }
};
</script>

<style>
</style>
