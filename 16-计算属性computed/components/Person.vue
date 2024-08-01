<template>
    <!-- html -->
    <div class="Person">
        姓:<input v-model="firstName"><br>
        名:<input v-model="lastName"><br>
        姓名:{{ name }}
        <button @click="changeName">名字替换为lisi</button>
    </div>

</template>


<script lang="ts" setup name="Person">
import { computed, ref } from 'vue';

let firstName = ref('jiang')
let lastName = ref('yi')
//计算属性的值 只读属性 不可修改 且会进行缓存
// let name=computed(() => {
//     return firstName.value.substring(0,1).toUpperCase()+firstName.value.substring(1)+'-'+lastName.value
// })
let name = computed({
    get() {
        return firstName.value.substring(0, 1).toUpperCase() + firstName.value.substring(1) + '-' + lastName.value
    },
    set(value) {
        console.log(value)
       const [str1,str2]=value.split('-')
        firstName.value=str1
        lastName.value=str2
    }
})
function changeName(){
    name.value='li-si'
}


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