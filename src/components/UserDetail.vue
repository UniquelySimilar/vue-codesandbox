<template>
  <div class="user-detail">
    <h3>User Detail</h3>
    <hr>
    <div class="row">
      <div class="col-md-6">
        <div class="row">
          <div class="col-md-3 font-weight-bold">ID</div>
          <div class="col-md-5">{{ user.id }}</div>
        </div>
        <div class="row">
          <div class="col-md-3 font-weight-bold">NAME</div>
          <div class="col-md-5">{{ user.name }}</div>
        </div>
        <div class="row">
          <div class="col-md-3 font-weight-bold">USER NAME</div>
          <div class="col-md-5">{{ user.username }}</div>
        </div>
        <div class="row">
          <div class="col-md-3 font-weight-bold">EMAIL</div>
          <div class="col-md-5">{{ user.email }}</div>
        </div>
        <div class="row">
          <div class="col-md-3 font-weight-bold">CITY</div>
          <div class="col-md-5">{{ user.address.city }}</div>
        </div>
        <div class="row">
          <div class="col-md-3 font-weight-bold">ZIP CODE</div>
          <div class="col-md-5">{{ user.address.zipcode }}</div>
        </div>
        <div class="row">
          <div class="col-md-3 font-weight-bold">PHONE</div>
          <div class="col-md-5">{{ user.phone }}</div>
        </div>
      </div>
    </div>
    <hr>
    <div class="row">
      <div class="col-md-6">
        <router-link class="btn btn-secondary" :to="{ name: 'users' }">Back</router-link>
      </div>
    </div>
  </div>
</template>

<script>
  import axios from 'axios'

  export default {
    props: {
      id: {
        type: Number,
        required: true
      }
    },
    data() {
      return {
        user: {
          address: {}
        }
      }
    },
    methods: {
      getUser() {
        axios.get('https://jsonplaceholder.typicode.com/users/' + this.id)
        .then( response => this.user = response.data )
        .catch( error => console.log(error) );
      }
    },
    created() {
      this.getUser();
    }
  }
</script>