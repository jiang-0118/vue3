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
    //数据，原来是写在data中的，此时的name，age，tel都不是响应式的数据
        import {ref} from 'vue'
        let name=ref('JY') //用ref修饰过的数据，从基本类型变为对象，需要操作对象.value修改属性值
        let age=ref(18)
        let tel='2501297332'
        
       function changeName(){
            name.value='zhangsan'//name改了但不是响应式的
        }
        function changeAge(){
            console.log(age.value)//age改了但不是响应式的
            age.value+=1
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