<template>
  <div v-if="seen" :title="tooltip" class="hello">{{ message }}</div>
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
      seen: true
    };
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
