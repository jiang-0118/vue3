<template>
    <!-- html -->
    <div class="Person">
        <h1>watch监视_情况3 监视【reactive】定义的【对象类型】数据</h1>
        <h3>我原来住{{ house.place }},{{ house.area }}平方</h3>
        <button @click="changePlace">点我地理+~</button>
        <button @click="changeArea">点我面积+1</button>
        <button @click="changeHouse">点我更换住址</button>
    </div>

</template>


<script lang="ts" setup name="Person">
import { reactive, watch } from 'vue';

    let house=reactive({
        place:'武汉',
        area:80
    })
    function changePlace(){
        house.place+='~'
    }
    function changeArea(){
        house.area+=1
    }
    function changeHouse(){
        //house={place:'孝感',area:60} 这种页面不会改动
        Object.assign(house,{place:'孝感',
        area:60})
    }
    //watch监视_情况3 监视【reactive】定义的【对象类型】数据,默认开启深度监视(deep:true)
    //当属性变化，对象变化都会被监听到
    //reactive定义的对象被修改时，不会改变地址
    watch(house,(newValue,oldValue)=>(
        console.log('house发生了变化',newValue,oldValue) 
    ))
    
    




</script>

<style>
/* 样式*/
.Person {
    background-color: skyblue;
    box-shadow: 0 0 10px;
    border-radius: 10px;
    padding: 20px;
    height: 200px;
}

button {
    margin-left: 20px;
}
</style>