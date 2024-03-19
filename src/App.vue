<template>
  <nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/map">Map</router-link> |
    <router-link to="/form-validation">Form Validation</router-link> |
    <router-link to="/local-storage">Local Storage</router-link> |
    <router-link to="/links">Links</router-link> 
  </nav>
  <router-view/>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #3686a8;
}
</style>
