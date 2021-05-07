<template>
  <div class="parent">
    <h4>Parent</h4>
    <hr>
    <child v-if="user" :userProp="user"/>
  </div>
</template>

<script>
  import axios from 'axios'
  import Child from './Child.vue'

  export default {
    components: {
      Child
    },
    data() {
      return {
        user: null
      }
    },
    methods: {
      getUser() {
        axios.get('https://jsonplaceholder.typicode.com/users/1')
          .then(response => this.user = response.data)
          .catch(error => console.log(error));
      }
    },
    created() {
      this.getUser();
    }
  }
</script>