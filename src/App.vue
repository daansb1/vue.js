<template>
  <TheHeader v-show="showHeader"></TheHeader>

  <div v-show="showName">
      Nome : {{ firstname }} <br>
      Sobrenome : {{ lastname }}
  </div>

  <div v-if="accessLevel === 'admin'">Admin</div>
  <div v-else-if="accessLevel === 'user'">User</div>
  <div v-else>Marketing</div>

  <div>

      <div v-for="(obj, index) in todos" v-bind:key="obj.title" class="todos-itens" >
        {{index}} - {{obj.title}}
      </div>

  </div>


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
        accessLevel: 'marketing',
        todos: [
          {
            "albumId": 1,
            "id": 1,
            "title": "accusamus beatae ad facilis cum similique qui sunt",
            "url": "https://via.placeholder.com/600/92c952",
            "thumbnailUrl": "https://via.placeholder.com/150/92c952"
          },
          {
            "albumId": 1,
            "id": 2,
            "title": "reprehenderit est deserunt velit ipsam",
            "url": "https://via.placeholder.com/600/771796",
            "thumbnailUrl": "https://via.placeholder.com/150/771796"
          },
          {
            "albumId": 1,
            "id": 3,
            "title": "officia porro iure quia iusto qui ipsa ut modi",
            "url": "https://via.placeholder.com/600/24f355",
            "thumbnailUrl": "https://via.placeholder.com/150/24f355"
          },
          {
            "albumId": 1,
            "id": 4,
            "title": "culpa odio esse rerum omnis laboriosam voluptate repudiandae",
            "url": "https://via.placeholder.com/600/d32776",
            "thumbnailUrl": "https://via.placeholder.com/150/d32776"
          },
          {
            "albumId": 1,
            "id": 5,
            "title": "natus nisi omnis corporis facere molestiae rerum in",
            "url": "https://via.placeholder.com/600/f66b97",
            "thumbnailUrl": "https://via.placeholder.com/150/f66b97"
          }
        ]
    }
  }
}
</script>

<style>
.todos-itens{
    background: crimson;
    margin: 0 0 5px 0;
    padding: 3px 6px;
    color: white;

}


#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
