<template>
  <div id="app">
    <Navigation></Navigation>
    <div class="container">
      <router-view/>
    </div>
  </div>
</template>

<script>
import Navigation from "./components/Navigation";

export default {
  name:"App",
  components:{
    Navigation
  }
}
</script>

<style>

</style>
