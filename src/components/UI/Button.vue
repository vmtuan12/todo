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
    <button @click="bamnut">Add task</button>
</template>