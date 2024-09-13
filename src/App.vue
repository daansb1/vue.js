<template>
  <TheHeader v-show="showHeader"></TheHeader>

  <div v-show="showName">
      Nome : {{ firstname }} <br>
      Sobrenome : {{ lastname }}
  </div>

  <div v-if="accessLevel === 'admin'">Admin</div>
  <div v-else-if="accessLevel === 'user'">User</div>
  <div v-else>Marketing</div>

  <img
      alt="Vue logo"
      src="./assets/logo.png"
  >
  <HelloWorld msg="Welcome to Your Vue.js App"/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import TheHeader from './components/TheHeader'

export default {
  name: 'App',
  components: {
    HelloWorld,
    TheHeader
  },
  data() {
    return {
        showHeader: true,
        firstname: 'Jon',
        lastname: 'Snow',
        showName: true,
        accessLevel: 'marketing'
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
