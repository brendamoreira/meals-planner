<template>
    <li>
        {{meal}} <button>-</button>
    </li>
</template>
<script>
export default {
    name: 'MealListItem',
    props:['meal']
}
</script>
<style scoped>

</style>