<template>
  <div id="app">
    <meals-list :meals="meals" @delete="removeItem" @addMeal="addMeal"/>
    <week-day-card :days="days"/>
    <button class="sort" @click="sortMeal"> Sort! </button>
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
      meals: ['Pizza', 'Lasanha', 'Macarrão', 'Batata', 'Pipoca'],
      days: [{name:'Monday', meal: ''}, {name:'Tuesday', meal: ''}, {name: 'Wednesday', meal:''}, {name: 'Thursday', meal: ''}, {name: 'Friday', meal: ''}, {name: 'Saturday', meal:''}, {name:'Sunday', meal:''}],
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
    },
    sortMeal(){
      this.days.forEach(day => { day.meal = this.meals[Math.floor(Math.random()*this.meals.length)]  
      });
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
