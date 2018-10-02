<template>
    <div id="app">
        <p 
            v-for="(item, index) in list" 
            @click="remove(index)"
            :key="index"
        >
            {{item}}
        </p>

        <input type="range" class="myrange">
        <input type="range" class="myrange">
        <input type="range" class="myrange">
        <input type="range" class="myrange">
        <input type="range" class="myrange">
        <input type="range" class="myrange">
        <input type="range" class="myrange">
        <input type="range" class="myrange">
        <button @click="average"></button>
        <p>{{average}}</p>
        <omgomgomg text="Add" @action="add"></omgomgomg>
    </div>    
</template>

<script>
import Prompt from './Prompt.vue'

export default {
    components: {'omgomgomg':Prompt},


    data: () => ({
        list: ["omg","wtf", "lol"],
        average: 0,
        values: []
    }),

    computed:{
        },

    methods: {
        calcAverage(){
            let ranges = document.querySelectorAll('.myrange')
            let sum = 0
            ranges.forEach( range => sum += range.value)
            sum /= ranges.length
            this.average = sum / ranges.length
        },
        add(text){
            this.list.push( text )
        },

        remove(index){
            this.list = this.list.filter( (item,itemIndex) => itemIndex != index)
        },

        doshit(){

        }
    }
}
</script>

<style scoped>
#app{
    background: peachpuff;
    width: 300px;
}

p{
    display: flex;
    justify-content: flex-end;
    width: 200px;
    margin: 5px;
    padding: 5px;
    background-color: hotpink;
    border: 3px solid pink;
    border-radius: 5px;
    transition: all 0.25s ease;
    cursor: pointer;
}

p:hover{
    background-color: pink;
    border: 3px solid hotpink;

}
</style>


