<template>
    <!-- html -->
     <div class="Person">
        <div>姓名：{{name}}</div>
        <div>年龄：{{age}}</div>
        <button @click="changeName">修改名字</button>
        <button @click="changeAge">修改年龄</button>
        <button @click="showTel">显示电话</button>
     </div>
    </template>
    
    <script>
    export default{
        name:'Person',//组件名
    setup(){
        //setup函数中的this是undefined Vue3中已经开始弱化this了
        //数据原来写在data中的，此时都不是响应式的
        let name='JY' //此时的name不是响应式的
        let age=18 //此时的age不是响应式的
        let tel='2501297332' //此时的tel不是响应式的
       function changeName(){
            name='zhangsan'//name改了但不是响应式的
        }
        function changeAge(){
            console.log(age)//age改了但不是响应式的
            age+=1
        }
        function  showTel(){
            alert(tel)
        }

        return{name,age,tel,changeName,changeAge,showTel}
        //set up的返回值也可以是一个渲染函数
        //return()=>'哈哈'

    }
    }
    //JS或TS
    </script>
    
    <style>
    /* 样式*/
    .Person{
        background-color: skyblue;
        box-shadow: 0 0 10px;
        border-radius: 10px;
        padding: 20px;
        height: 200px;
    }
    .button{
        margin-left: 20px;
    }
    </style>