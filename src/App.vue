<template>
  <div id="app"> <!--  single file component + nav with 2 links-->
   <div id="nav">   
      <router-link to="/">Home</router-link> | <!--router-link permet de naviguer à partir de l' html de façon statique-->
      <router-link to="/about">About</router-link>
   </div>
    <router-view/> <!--where our component is displayed (view) defini dans router.js-->
    </div>
</template>

<script>
export default {
  
}
</script>


<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
#nav {
  padding: 30px;
  a {
    font-weight: bold;
    color: #2c3e50;
    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
