<template>
  <div id="app">
    <nav>
      <router-link to="/">Inicio</router-link> |
      <router-link to="/juegos">Juegos</router-link>
    </nav>
    <router-view />
  </div>
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
  /*background-color: #45e4f6;*/
}

nav a {
  font-weight: bold;
  color: rgb(228, 97, 178);
}

nav a.router-link-exact-active {
  color: rgb(85, 211, 225);
}
body {
  background-image: url("assets/fondo.jpg");

  background-size: cover;
}
</style>
