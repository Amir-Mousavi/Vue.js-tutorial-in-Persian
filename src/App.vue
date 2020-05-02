
<template>
  <div id="app">
    {{ reversedMessage }}

    <p />

    <div>
      {{ fullName }}
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      message: 'Goodbye',
      firstName: 'John',
      lastName: 'Due',
    }
  },
  computed: {
    reversedMessage() {
      return this.message.split('').reverse().join('');
    },
    fullName() {
      return `${this.firstName} ${this.lastName}`
    }
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
