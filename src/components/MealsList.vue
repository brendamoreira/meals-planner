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
    font-family: 'Josefin Sans', sans-serif;
    position: relative;
    align-content: center;
    color: tomato;
    padding: 3px 8px;
}

.new-meal {
    font-family: 'Josefin Sans', sans-serif;
    width: 150px;
    text-align: center;
    margin: 5px 5px 10px 5px;
    padding: 3px;
    border: 0.5px solid rgb(255, 99, 71);
    border-radius: 3px;
}
</style>