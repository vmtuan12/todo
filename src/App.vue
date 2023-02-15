<script setup>
import TodoList from './components/Todo/TodoList.vue';


</script>

<template>
    <div class="title">To-do List</div>
    <TodoList/>
</template>

<style scoped>
    .title {
        color: aliceblue;
        display: flex;
        justify-content: center;
        font-size: 40px;
        text-shadow: 0 10px 10px black;
        transition: font-size 2s;
        width: fit-content;
        margin: auto;
    }
    .title:hover {
        font-size: 60px;
    }
</style>
