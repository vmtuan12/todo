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

</style>