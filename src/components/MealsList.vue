<template>
    <aside>
        <ul>
        <meal-list-item v-for="meal in meals" :key="meal" :meal="meal" />
        </ul>
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

</style>