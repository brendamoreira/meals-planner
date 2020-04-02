<template>
  <div id="app">
    <meals-list :meals="meals" @delete="removeItem" @addMeal="addMeal"/>
    <week-day-card/>
    <button class="sort"> Sort! </button>
  </div>
</template>

<script>
import MealsList from "./components/MealsList.vue"
import WeekDayCard from"./components/WeekDayCard.vue"

export default {
  name: 'App',
  components:{
    MealsList,
    WeekDayCard
  },
  data() {
    return{
      meals: ['Pizza', 'Lasanha', 'Macarrão', 'Batata', 'Pipoca']
    }
  },
  methods:{
    removeItem(name){
      this.meals = this.meals.filter(function(meal){
        return meal != name;
      }, 1);
    },
    addMeal(newMeal){
      if(!this.meals.map(m => m.toLowerCase()).includes(newMeal.toLowerCase())){
        this.meals.push(newMeal)
      } else{
        alert('This meal already exists')
      }
      
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
  display: flex;
}
.sort {
  position: absolute;
  bottom: 15px;
  right: 30px;
}
</style>
