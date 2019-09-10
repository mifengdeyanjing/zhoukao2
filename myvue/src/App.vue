<template>
  <div id="app">
    <!-- <img src="./assets/logo.png"> -->
    <Home/>
    <router-view/>
  </div>
</template>

<script>
import Home from "./components/home"
export default {
  name: 'App',
  components:{Home}
}
</script>

<style>

</style>
