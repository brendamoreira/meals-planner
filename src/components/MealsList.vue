<template>
    <aside class="sidebar">
        <h2> Meals </h2>
        <ul>
        <meal-list-item v-for="meal in meals" :key="meal" :meal="meal" @delete="$emit('delete', meal)"/>
        </ul>
        <button class="bottom">Add meal + </button>
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
}
</script>
<style scoped>
.sidebar {
    width: 30%;
    text-align: center;
    border-right: 3px dashed tomato;
}
h2 {
    text-decoration: underline wavy tomato;
}
ul {
    padding: 0;
}
.bottom {
  position: relative;
  align-content: center;
}
</style>