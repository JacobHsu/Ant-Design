<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <a-button type="primary">Primary</a-button>
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'app',
  components: {
    HelloWorld
  }
}
</script>

