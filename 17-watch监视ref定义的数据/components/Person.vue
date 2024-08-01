<template>
    <!-- html -->
    <div class="Person">
        <h1>watch监视_情况1 监视【ref】定义的【基本类型】数据</h1>
        <h3>当前求和为：{{ sum }}</h3>
        <button @click="changeSum">点我sum+1</button>
    </div>

</template>


<script lang="ts" setup name="Person">
import { computed, ref, watch } from 'vue';

let sum=ref(0)
function changeSum(){
    sum.value+=1
}
const stopWatch=watch(sum,(newValue,oldValue)=>{
    console.log("newValue:"+newValue,"oldValue:"+oldValue)
    //当sum的value属性大于10时，停止监视
    // if(sum.value>=10){
    //     stopWatch()
    // }
})




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