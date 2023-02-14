<script>
export default {
    props: ['modelValue', 'placeHolder'],
    emits: ['update:modelValue'],
    
}
</script>

<template>
    <input
        :value="modelValue"
        :placeholder="placeHolder"
        @input="$emit('update:modelValue', $event.target.value)"
    />
</template>

<style scoped>
    input {
        border-radius: 7px;
        border: 2px solid black;
    }
    input:focus {
        background-color: antiquewhite;
    }
</style>