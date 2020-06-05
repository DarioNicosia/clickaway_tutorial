<template>
  <div id="app">
    <div id="nav">
      <h3 class="nav-right">VUEDEV</h3>
      <Dropdown/>
      <router-link v-if="aboutRoute" to="/">Home</router-link>
      <router-link v-else to="/about">About</router-link>
    </div>
    <router-view/>
  </div>
</template>

<script>
import Dropdown from '../src/components/Dropdown'
export default {
  name:'app',
  components:{
    Dropdown
  },
  computed:{
    aboutRoute(){
       return this.$route.name === 'About'
    }
  }
}
</script>

<style>
*{
  padding: 0;
  margin:0;
  box-sizing: border-box;
  background-color: #F5F5F5;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  
}

#nav {
  padding: 30px;
  display:flex;
  justify-content: flex-end;
  margin-bottom: 30px;
 
  align-items: center;
  background-color: #FAFAFA;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
  text-decoration: none;
  background-color: transparent;
}

.nav-right{
	margin-right:auto;
  border:2px solid #2c3e50;
  padding: 5px 8px;
  color: #009688;
  background-color: #FAFAFA;
}

#nav a.router-link-exact-active {
  color: #42b983;
}
</style>
