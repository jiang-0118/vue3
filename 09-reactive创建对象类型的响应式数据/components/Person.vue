<template>
    <!-- html -->
     <div class="Person">
        <h2>游戏列表：</h2>
        <ui>
            <li v-for="g in games" :key="g.key">
                key：{{g.key}} name：{{g.name}}
            </li>
            </ui>
            <button @click="changeKey">修改第一个游戏的键</button>
        <button @click="changeName">修改第一个游戏的名</button>
     </div>
    </template>
    
   
    <script lang="ts" setup name="Person">
    //数据，原来是写在data中的，此时的name，age，tel都不是响应式的数据
        import {reactive} from 'vue'
        let games=reactive([
            {key:1,name:'lol'},
            {key:2,name:'pubg'},
            {key:3,name:'qq'}
        ])
        function changeKey(){
            games[0].key+=1
        }
        function changeName(){
            games[0].name='英雄联盟'
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