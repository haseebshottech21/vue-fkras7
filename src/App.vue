<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="https://vuejs.org/images/logo.png" /> -->
    <!-- <EmployeeList /> -->
    <PostComponent />
  </div>
</template>

<script>
// import EmployeeList from './components/EmployeeList.vue';
import PostComponent from './components/PostComponent.vue';

export default {
  name: 'App',
  components: {
    // EmployeeList,
    PostComponent,
  },
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
