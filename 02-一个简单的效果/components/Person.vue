<template>
    <!-- html -->
     <div class="Person">
        <div>姓名：{{this.name}}</div>
        <div>年龄：{{this.age}}</div>
        <button @click="changeName">修改名字</button>
        <button @click="changeAge">修改年龄</button>
        <button @click="showTel">显示电话</button>
     </div>
    </template>
    
    <script>
    export default{
        name:'Person',//组件名
        methods:{
            changeName(){
                this.name='zhang-san'
            },
            changeAge(){
                this.age+=1
            },
            showTel(){
                alert(this.tel)
            }
        }
        ,
        data(){
            return{
                name:'张三',
                age:18,
                tel:'123456789'
            }
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