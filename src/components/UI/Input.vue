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
        border: 1.5px solid black;
        border-radius: 8px;

    }
    input:focus {
        background-color: antiquewhite;
    }
</style>