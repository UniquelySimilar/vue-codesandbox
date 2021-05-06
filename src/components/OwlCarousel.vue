<template>
  <div class="owl-carousel owl-theme">
    <div class="item">
      <h4>1</h4>
    </div>
    <div class="item">
      <h4>2</h4>
    </div>
    <div class="item">
      <h4>3</h4>
    </div>
    <div class="item">
      <h4>4</h4>
    </div>
    <div class="item">
      <h4>5</h4>
    </div>
    <div class="item">
      <h4>6</h4>
    </div>
    <div class="item">
      <h4>7</h4>
    </div>
    <div class="item">
      <h4>8</h4>
    </div>
    <div class="item">
      <h4>9</h4>
    </div>
    <div class="item">
      <h4>10</h4>
    </div>
  </div>
</template>

<script>
  import axios from 'axios'

  import $ from 'jquery'
  import 'owl.carousel/dist/assets/owl.carousel.css';
  import 'owl.carousel/dist/assets/owl.theme.default.css'
  import 'owl.carousel';

  export default {
    data() {
      return {
        users: [],
      }
    },
    computed: {
      displayCarousel() {
        return (this.users.length > 0)
      }
    },
    methods: {
      getUsers() {
        axios.get('https://jsonplaceholder.typicode.com/users')
          .then(response => {
            this.users = response.data;
            this.initCarousel();
          })
          .catch(error => console.log(error))
      },
      initCarousel() {
        $(".owl-carousel").owlCarousel({
          loop: true,
          margin: 10,
          nav: true,
          responsive: {
            0: {
              items: 1
            },
            600: {
              items: 3
            },
            1000: {
              items: 5
            }
          }
        })
      }
    },
    mounted() {
      this.getUsers();
    }
  }
</script>

<style scoped>
  .item {
    background-color: rgb(185, 231, 185);
  }
</style>