<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <p>
      Vote for the winner!
    </p>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.hello h1 {
  text-shadow: 1px 1px #2c3e50;
}
</style>
