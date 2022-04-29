<template>
  <div id="app">
    <List :list="list" @user-details="(data) => (userDetailsData = data)" />
    <UserDetail :userData="userDetailsData" />
  </div>
</template>

<script>
import List from "./components/List";
import UserDetail from "./components/UserDetail";

export default {
  name: "App",
  data() {
    return {
      list: [],
      userDetailsData: {},
    };
  },
  components: {
    List,
    UserDetail,
  },
  mounted() {
    fetch("https://jsonplaceholder.typicode.com/users")
      .then((response) => response.json())
      .then((result) => this.list.push(result));
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
