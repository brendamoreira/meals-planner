<template>
    <li>
        {{meal}} <button @click="$emit('delete')">-</button>
    </li>
</template>
<script>
export default {
    name: 'MealListItem',
    props:['meal']
}
</script>
<style scoped>
li {
    list-style: none;
    margin: 10px;
}
</style>