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
        border: 2px solid rgb(81, 81, 81);
    }
    input:focus {
        background-color: rgb(81, 81, 81);
        color: white;
    }
</style>