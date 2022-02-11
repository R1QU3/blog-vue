<template>
  <div id="nav">
    <router-link to="/">Home</router-link>
    <router-link to="/blog">Blog</router-link>
  </div>
  <router-view/>
</template>

<style>

body {
  color: #fff;
  background: #141414;
}

#app {
  font-family: 'Fira Sans', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  /* color: #2c3e50; */
}

#nav {
  padding: 30px;
  display: flex;
  justify-content: center;
  gap: 1.2rem;
  margin: 0 auto;
}

#nav a {
  padding: .5rem 1rem;
  border-radius: 5px;
  text-decoration: none;
  font-weight: bold;
  color: #42b983;
}

#nav a.router-link-exact-active {
  background: #af8;
  color: #007542;
  }
</style>
