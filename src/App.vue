<template>
  <div id="app">
    <nav>
      <router-link to="/">Todo</router-link>|
      <router-link to="/currency">Currency</router-link>|
      <router-link to="/movie">Movie</router-link>
    </nav>
    <router-view />
  </div>
</template>

<style>
body {
  height: 100vh;
  background: linear-gradient(#414d59, #b1bfc1) no-repeat;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #7d8286;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  margin: 0 20px;
  color: #86b0b2;
  text-decoration: none;
}

nav a.router-link-exact-active {
  color: #cde2e1;
  text-decoration: none;
}
</style>
