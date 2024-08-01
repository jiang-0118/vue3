<template>
    <!-- html -->
    <div class="Person">
        名字：{{ name }}
        <br>
        年龄：{{ age }}
        <br>
        <button @click="changeName">修改名字</button>
        <button @click="changeAge">修改年龄</button>
    </div>

</template>


<script lang="ts" setup name="Person">
import { reactive, ref, toRefs, toRef } from 'vue';
//数据
let person = reactive({
    name: 'jy',
    age: 18
})
//该方法相当于将name和age变为ref(name)和age(name)并于person.name person.age类似双向绑定
let { name, age } = toRefs(person)

//方法
function changeName() {
    person.name += '~'
    //name.value+='~'
    console.log(name)
    console.log(person.name)
}
function changeAge() {
    person.age += 1
    //age.value+=1
    console.log(age)
    console.log(person.age)
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

.button {
    margin-left: 20px;
}
</style>