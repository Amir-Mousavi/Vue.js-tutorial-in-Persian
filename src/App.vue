
<template>
  <div class="container" :class="{ active: isActive }" :style="{ border: hasError ? '2px solid red' : 'default' }">
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      isActive: true,
      hasError: false,
    }
  },
};
</script>

<style>
  .container {
    width: 200px;
    height: 200px;
    border: 1px solid #ccc;
  }

  .active{
    border: 3px solid blue;
  }
</style>
