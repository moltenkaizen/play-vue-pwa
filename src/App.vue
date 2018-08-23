<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <div v-if="users.length > 0" class="profiles">
      <user-profile v-for='user in users' :key="user.email" :user=user ></user-profile>
    </div>
  </div>
</template>

<script>
import UserProfile from './components/UserProfile.vue'

export default {
  name: 'app',
  data () {
    return {
      users: []
    }
  },
  components: {
    UserProfile
  },
  mounted () {
    fetch('https://randomuser.me/api/?results=30')
      .then(results => results.json())
      .then(data => {
        this.users = data.results
    }).catch(error => console.log(error))
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.profiles {
  display: flex;
  justify-content: center;
  flex-flow: row wrap;
}
</style>
