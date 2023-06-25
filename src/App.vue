<template>
  <div id="app">
    <router-link to="/">Home</router-link> |
    <router-link to="/addCompany">Add Company</router-link>

    <router-view/>
  </div>
</template>

<script>

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

header {
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #f2f2f2;
  padding: 20px;
}

.nav-button {
  display: flex;
  justify-content: center;
  align-items: center;
  width: auto;
  height: auto;
  padding: 1%;
  border-radius: 5px;
  background-color: #42b983;
  color: white;
  font-size: 16px;
  font-weight: bold;
  text-decoration: none;
  margin: 0 10px;
}

.nav-button:hover {
  background-color: #5cd6a0;
}

.nav-button.router-link-exact-active {
  background-color: #2c3e50;
}
</style>
