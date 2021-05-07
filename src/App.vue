<template>
  <div id="app" class="container">
    <parent />
  </div>
</template>

<script>
  import Parent from '@/components/current/Parent'

  export default {
    name: 'App',
    components: {
      Parent
    },
  }
</script>