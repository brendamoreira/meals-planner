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
@import url('https://fonts.googleapis.com/css2?family=Fredericka+the+Great&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Clicker+Script&family=swap');

h4{
    font-family: 'Fredericka the Great', cursive;
    font-weight: 100;
    font-size: 1.2rem;
    margin: 0;
    text-decoration: underline solid rgba(0, 0, 0, 0.523);
}
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
p {
    font-family: 'Clicker Script', cursive;
    font-size: 1.3rem;
    color: tomato;
}
</style>