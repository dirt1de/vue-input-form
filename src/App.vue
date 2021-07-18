<template>
  <Form></Form>
</template>

<script>
import Form from "./components/Form.vue"

export default {
  name: 'App',
  components: {
    Form
  }
}
</script>

<style>
body{
  background-color: rgb(167, 167, 167);
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  justify-content: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
