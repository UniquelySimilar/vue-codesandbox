<template>
  <div class="child">
    <h5>Child</h5>
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
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    props: {
      userProp: {
        type: Object,
        required: true
      }
    },
    data() {
      return {
        user: this.userProp
      }
    }
  }
</script>