<template>
    <!-- html -->

    <Parent></Parent>


</template>

<script>
import Parent from './components/Person.vue'
export default {

    name: 'App', //组件名
    components: { Parent } //注册组件
}

//JS或TS
</script>

<style>
/* 样式*/
.app {
    background-color: #ddd;
    box-shadow: 0 0 10px;
    border-radius: 10px;
    padding: 20px;
    height: 400px;
}
</style>