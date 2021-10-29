<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/browse">Browse</router-link> |
      <router-link to="/ranking">Ranking</router-link> |
      <router-link to="/about">About</router-link>
    </div>
    <router-view/>
  </div>
</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #a1cffd;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #ff6767;
}

#nav a.router-link-exact-active {
  color: #ffdddd;
}
</style>
