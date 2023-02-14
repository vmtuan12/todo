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
        border-radius: 12px;
        border: none;
        background-color: aliceblue;
        /* 182 */
        cursor: pointer;
        padding: 5px;
    }
    button:hover {
        background-color: black;
        color: aliceblue;
    }
</style>