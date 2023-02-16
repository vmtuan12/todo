<script>
    export default {
        methods: {
            onClickHandler() {
                this.$emit('clicked')
            }
        }
    }
</script>

<template>
    <div class="modal-back" @click="onClickHandler">
        
    </div>
</template>

<style scoped>
    .modal-back {
        position: fixed;
        top: 0;
        left: 0;
        width: 100vw;
        height: 100vh;
        z-index: 100;
        background: rgba(0, 0, 0, 0.75);
    }
</style>