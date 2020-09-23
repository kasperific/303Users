<template>
  <div class="user-list">
    <h1>List of Users</h1>
    <ul v-for="user in users"  :user="user" :key="user.id">
      <li>
        <UserCard :user="user"  />
      </li>
    </ul>
  </div>
</template>

<script>
import axios from 'axios'
import UserCard from '@/components/UserCard'

export default {
  name: 'UserList',
  components: {
    UserCard
  },
  data () {
    return {
      users: []
    }
  },
  created () {
    this.getUsers()
  },
  methods: {
    getUsers () {
      var self = this
      const url = 'https://jsonplaceholder.typicode.com/users'
      axios
        .get(url)
        .then(response => (self.users = response.data))
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
