<template>
  <div id="app">
    <meals-list :meals="meals"/>
  </div>
</template>

<script>
import MealsList from "./components/MealsList.vue"

export default {
  name: 'App',
  components:{
    MealsList
  },
  data() {
    return{
      meals: ['pizza', 'lasanha', 'macarrão']
    }
  }
}
</script>

<style>
* {
  box-sizing: border-box;
}
html, body {
  margin: 0;
  padding: 0;
  width: 100vw;
  height: 100vh;
}
#app {
  width: 100vw;
  height: 100vh;
}
</style>
