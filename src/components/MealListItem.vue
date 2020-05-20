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

button {
    background-color: white;
    color:tomato;
    border-color: rgba(255, 99, 71, 0.427);
    border-radius: 4px;
}
</style>