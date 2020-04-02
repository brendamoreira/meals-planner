<template>
    <div>
        <ul>
            <li v-for="day in days" :key="day">
                {{day}}
            </li>
        </ul>
    </div>
</template>
<script>
export default {
    data(){
        return{
            days:['Monday','Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday', 'Sunday']
        }
    }
    
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