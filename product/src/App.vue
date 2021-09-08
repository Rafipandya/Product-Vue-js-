// App.vue

<template>
  <div id="app">
    <Products />
  </div>
</template>

<script>
import Products from './components/Product.vue'

export default {
  name: 'app',
  components: {
    Products
  }
}
</script>

<style>
* {
  background-color: whitesmoke;

}

#app {
  font-family: 'montserrat', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: black;
  font-weight: bolder;
  margin-top: 100px;
  margin-bottom: 50px;
}

</style>


