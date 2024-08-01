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
    
   
    <script lang="ts" setup name="Person">
        
        let name='JY' 
        let age=18 
        let tel='2501297332'
        
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