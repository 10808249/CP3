<template>
  <div class="home">
    <img class="home-logo" alt="Vue logo" src="../assets/Worlds_2021.webp">
    <HelloWorld msg="Welcome to 2021 World Championship!"/>
    <hr>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  components: {
    HelloWorld
  }
}
</script>

<style>
img.home-logo {
  width:40%;
}
</style>
