<template>
<div >


</div>
  <HelloWorld/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
 
  components: {
    HelloWorld
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  margin: 50px;
  color: #2c3e50;
  margin-top: 60px;
}
.navbar {
 height: 110px;
  background: rgb(218, 218, 255);
  border: 1px solid black;
  margin: 40px;
}

</style>
