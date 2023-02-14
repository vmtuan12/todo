<script>
export default {
    methods: {
        bamnut() {
            this.$emit('pressed')
        }
    }
}
</script>

<template>
    <button @click="bamnut">
        <slot></slot>
    </button>
</template>

<style scoped>
    button {
        border-radius: 15px;
        border: 2px solid black;
        background-color: aliceblue;
        cursor: pointer;
        padding: 5px;
        
    }
    button:hover {
        background-color: black;
        color: aliceblue;
    }
    
</style>