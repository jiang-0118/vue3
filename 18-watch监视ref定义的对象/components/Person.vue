<template>
    <!-- html -->
    <div class="Person">
        <h1>watch监视_情况2 监视【ref】定义的【对象类型】数据</h1>
        <h3>我原来住{{ house.place }},{{ house.area }}平方</h3>
        <button @click="changePlace">点我地理+~</button>
        <button @click="changeArea">点我面积+1</button>
        <button @click="changeHouse">点我更换住址</button>
    </div>

</template>


<script lang="ts" setup name="Person">
import { computed, ref, watch } from 'vue';

    let house=ref({
        place:'武汉',
        area:80
    })
    function changePlace(){
        house.value.place+='~'
    }
    function changeArea(){
        house.value.area+=1
    }
    function changeHouse(){
        house.value={place:'孝感',
        area:60}
    }
    //watch监视_情况2 监视【ref】定义的【对象类型】数据
    //监视函数 第一个参数：监视的对象or值
    //监视函数 第二个参数：监视的对象变化前的值，变化后的值
    //监视函数 第三个参数：监视函数的其他配置 
    //deep为false时，当监视的对象被改动时才会生效；deep为true时，当监视的对象的属性被改动时也会生效：属性改变时，new和old是相同的；对象改变时，new和old不同
    watch(house,(newValue,oldValue)=>{
        console.log('house发生了变化',newValue,oldValue)
    },{deep:true})
    //




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