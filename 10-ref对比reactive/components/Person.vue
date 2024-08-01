<template>
    <!-- html -->
     <div class="Person">
        <ui>
            <li v-for="c in cars">
                一辆{{c.brand}}，价值{{c.price}}
            </li>
        </ui>
        一辆{{car.brand}}，价值{{car.price}}
        <button @click="changePrice">
            点击修改价格
        </button>
        <button @click="changeBrand">
            点击修改品牌
        </button>
        <button @click="changeCar">
            点击修改车
        </button>
       
     </div>
    </template>
    
   
    <script lang="ts" setup name="Person">
    import { reactive,ref } from 'vue';
    //reactive使用
    let cars=reactive([
        {brand:'牛马',price:1},
        {brand:'牛头',price:2}
    ])
    let car=reactive({brand:'玛莎',price:100000})
    function changePrice(){
       cars[0].price+=1
    }
    function changeBrand(){
        cars[0].brand='鬼子'
    }
    function changeCar(){
        //car={brand:'鬼鬼鬼',price:100000}
        // car=reactive({brand:'鬼鬼鬼',price:100000}) 页面更新不了
        // car.brand='鬼鬼鬼' 页面可以更新
        // car.price=1 页面可以更新
      //Object.assign(car,{brand:'鬼鬼鬼',price:100000}) 页面可以更新
    }
    //ref使用
    // let cars=ref([
    //     {brand:'牛马',price:1},
    //     {brand:'牛头',price:2}
    // ])

    // function changePrice(){
    //    cars.value[0].price+=1
    // }
    // function changeBrand(){
    //     cars.value[0].brand='鬼子'
    // }
    // function changeCar(){
    //     cars.value[0]={brand:'神驹',price:10000}
    // }
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