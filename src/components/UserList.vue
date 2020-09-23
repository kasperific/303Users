<template>
  <div class="user-list-section">
    <h1>List of Users</h1>
    <ul>
      <li v-for="user in users"  :user="user" :key="user.id">
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

ul {
  list-style-type: none;
  padding: 0;
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  grid-gap: 1rem;
}
li {
  display: inline-block;
  margin: 0 10px;
}

</style>
