<script>
    export default {
        emits: ['modalOff'],
        methods: {
            turnOffModal() {
                this.$emit('modalOff')
            }
        }
    }
</script>

<script setup>
import ModalBack from '../UI/ModalBack.vue'
import Button from '../UI/Button.vue'

</script>

<template>
    <ModalBack @clicked="turnOffModal"/>
    <div class="modal">
        <div class="msg">Error</div>
        <div class="btn">
            <Button @pressed="turnOffModal">OK</Button>
        </div>
    </div>
</template>

<style scoped>
    .modal {
        display: flex;
        flex-direction: column;
        width: 300px;
        height: 200px;
        border: 1.5px solid black;
        border-radius: 12px;
        background-color: aliceblue;
        align-items: center;
        justify-content: center;
        position: fixed;
        z-index: 999;
        margin-top: 2rem;
        animation: modal-appear 1s ease-in-out forwards;
    }

    @keyframes modal-appear {
        from {
            opacity: 0;
            transform: scaleX(0.3);
        }
        to {
            opacity: 1;
            transform: scaleX(1);
        }
    }

    .msg {
        position: fixed;
    }

    .btn {
        margin-top: 100px;
    }
</style>