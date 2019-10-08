<template>
  <div id="app">
   <employee-form/>
  </div>
</template>

<script>
import EmployeeForm from "./components/EmployeeForm.vue";

export default {
  name: "app",
  components: {
    EmployeeForm
  }
};
</script>

<style lang="scss">
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
