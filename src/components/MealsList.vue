<template>
    <aside class="sidebar">
        <h2> Meals </h2>
        <ul>
        <meal-list-item v-for="meal in meals" :key="meal" :meal="meal" @delete="$emit('delete', meal)"/>
        </ul>
        <input v-model="newMeal" class="new-meal" placeholder="New Meal">
        <button class="bottom" @click="emitNewMeal">Add meal + </button>
    </aside>
</template>
<script>
import MealListItem from "./MealListItem.vue"
export default {
    name:'MealsList',
    props:['meals'],
    components: {
        MealListItem
    },
    data(){
        return{
            newMeal: '',
        }
    },
    methods: {
        emitNewMeal(){
            if(this.newMeal.trim() !== ''){
                this.$emit('addMeal', this.newMeal);
                this.newMeal= '';
            }
        }
    }
}
</script>
<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Josefin+Sans:wght@200&display=swap');

.sidebar {
    width: 30%;
    text-align: center;
    border-right: 3px dashed tomato;
    font-family: 'Josefin Sans', sans-serif;
}
h2 {
    font-family: 'Josefin Sans', sans-serif;
    font-size: 2rem;
    text-decoration: underline wavy tomato;
}
ul {
    padding: 0;
}
.bottom {
  position: relative;
  align-content: center;
}
.new-meal {
    text-align: center;
}
</style>