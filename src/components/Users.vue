<template>
  <div class="users">
    <h3>Users</h3>
    <div class="row">
      <div class="col-md-6">
        <table class="table table-bordered table-sm">
          <thead>
            <tr>
              <th>ID</th>
              <th>NAME</th>
              <th>EMAIL</th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="user in users" :key="user.id">
              <td>
                <router-link :to="{ name: 'userDetail', params: { id: user.id } }">{{ user.id }}</router-link>
              </td>
              <td>{{ user.name }}</td>
              <td>{{ user.email }}</td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>
  </div>
</template>

<script>
  import axios from 'axios'

  export default {
    name: 'Users',
    data() {
      return {
        users: []
      }
    },
    methods: {
      getUsers() {
        axios.get('https://jsonplaceholder.typicode.com/users')
        .then( response => this.users = response.data )
        .catch( error => console.log(error) )
      }
    },
    created() {
      this.getUsers();
    }
  }
</script>