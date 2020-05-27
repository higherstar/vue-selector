<template>
  <div id="app">
    <customize-path></customize-path>
  </div>

</template>

<script>
  import CustomizePath from "./views/CustomizePath";

  export default {
    name: 'app',
    components: {CustomizePath}
  }
</script>

<!-- Global CSS -->
<style>

</style>

<!-- Scoped component css -->
<!-- It only affect current component -->
<style scoped>
  #app {
    background: #797979;
    height: 100vh;
    padding: 50px;
  }
</style>
