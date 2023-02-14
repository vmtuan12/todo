<script setup>
</script>

<template>
    <div class="item">
        <div class="inp">
            <slot name="inputTitle"></slot>
            <slot name="inputDescription"></slot>
        </div>
        <div class="btn">
            <slot name="button"></slot>
        </div>
    </div>
</template>

<style scoped>
    .item {
        display: flex;
        align-items: center;
        justify-content: center;
        padding: 15px 0px;
        max-width: 600px;
        border-radius: 10px;
        border: 1.5px solid black;
        margin: auto;
        max-width: 600px;
        background-color: whitesmoke;
        box-shadow: 0 2px 8px rgba(0, 0, 0, 0.66);
    }
</style>