<template>
  <div>
    <div v-if="seen" :title="tooltip" class="hello">{{ message }}</div>
    <div v-else>that's the else part</div>
    <p />

    <div v-for="item in todos" :key="item.text">{{ item.text }}</div>

    <p />

    <button @click="reverseMessage">reverse the message</button>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  data: () => {
    return {
      message: "Hello Guys, welcome to Vue",
      tooltip: "this is a tooltip!!!",
      seen: true,

      todos: [
        { text: "Learn JavaScript" },
        { text: "Learn Vue" },
        { text: "Build something awesome" }
      ]
    };
  },
  methods: {
    reverseMessage: function() {
      this.message = this.message
        .split("")
        .reverse()
        .join("");
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
