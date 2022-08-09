<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <PunchBag />
    <HelloWorld />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import PunchBag from './components/PunchBag.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    PunchBag
}
}
</script>

<style>


</style>
