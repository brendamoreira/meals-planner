<template>
    <div>
        <ul>
            <li v-for="day in days" :key="day.name">
                <h4>{{ day.name }}</h4> 
                <p>{{ day.meal }}</p>
            </li>
        </ul>
    </div>
</template>
<script>
export default {
    name: 'WeekDayCard',
    props: ['days'],
    
}
</script>
<style scoped>
ul {
    display: flex;
    flex-wrap: wrap;
}
li {
    text-align: center;
    width: 120px;
    height: 150px;
    padding: 8px;
    margin: 20px;
    list-style: none;
    border: 4px double tomato;
}
</style>