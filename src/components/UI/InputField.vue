<script setup>
</script>

<template>
    <div class="item">
        <div class="inp">
            <slot name="input"></slot>
        </div>
        <div class="btn">
            <slot name="button"></slot>
        </div>
    </div>
</template>

<style scoped>
    .item {
        display: flex;
        border-radius: 10px;
        border: 1.5px solid black;
        margin: auto;
        max-width: 600px;
        align-items: center;
        justify-content: center;
        padding: 5px 0px;
        gap: 5px;
    }
</style>