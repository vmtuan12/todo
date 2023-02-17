<script>
    export default {
        data() {
            return {
                list: [],
                id: 0,
                title: '',
                errorInput: false,
                description: ''
            }
        },
        methods: {
            addTodo() {
                if(this.title === '' || this.description === '') {
                    this.errorInput = true
                    return;
                }
                this.list.push({
                    id: this.id++,
                    title: this.title,
                    description: this.description
                })
                this.title = ''
                this.description = ''
            },
            removeTodo(id) {
                const removedItemIndex = this.list.findIndex((e) => e.id === id)
                console.log(removedItemIndex);
                this.list.splice(removedItemIndex, 1)
                if(this.list.length === 0) {
                    this.id = 0
                }
            },
            removeModal() {
                this.errorInput = false
            }
        }
    }
</script>

<script setup>
import Card from '../UI/Card.vue';
import InputField from '../UI/InputField.vue';
import Input from '../UI/Input.vue';
import Button from '../UI/Button.vue';
import ErrorModal from '../UI/ErrorModal.vue'

</script>

<template>
    <a class="bigTitle" href="#/">To-do List</a>
    <div v-if="errorInput" class="error-modal">
        <ErrorModal @modalOff="removeModal"/>
    </div>
    
    <InputField>
        <template #inputTitle>
            <Input v-model="title" placeHolder="Title"/>
        </template>
        <template #inputDescription>
            <Input v-model="description" placeHolder="Description"/>
        </template>
        <template #button>
            <Button @pressed="addTodo">Add Task</Button>
        </template>
    </InputField>
    <template v-for="item in list" :key="item.id">
        <Card>
            <template #checked>
                <input type="checkbox" id="checkbox"/>
            </template>
            <template #index>{{ list.indexOf(item) }}</template>
            <template #heading>Task: {{ item.title }}</template>
            <template #info>Task description: {{ item.description }}</template>
            <template #button>
                <Button @pressed="removeTodo(item.id)">Remove todo</Button>
            </template>
        </Card>
    </template>
</template>

<style scoped>
    .error-modal {
        display: flex;
        justify-content: center;
    }

    .bigTitle {
        color: aliceblue;
        display: flex;
        justify-content: center;
        font-size: 40px;
        text-shadow: 0 10px 10px black;
        transition: font-size 0.75s;
        width: fit-content;
        margin: auto;
        text-decoration: none;
        /* animation: shake 0.82s cubic-bezier(0.36, 0.07, 0.19, 0.97) both; */
        animation: out 0.5s;
        transform: translate3d(0, 0, 0);
    }
    .bigTitle:hover {
        font-size: 45px;
        color: black;
        animation: in 0.5s ease-in-out;
    }
    @keyframes in {
        from {
            /* transform: rotate(0deg); */
            font-size: 40px;
            color: aliceblue;
        }
        to {
            /* transform: rotate(360deg); */
            font-size: 45px;
            color: black;
        }
    }
    @keyframes out {
        from {
            /* transform: rotate(360deg); */
            font-size: 45px;
            color: black;
        }
        to {
            /* transform: rotate(0deg); */
            font-size: 40px;
            color: aliceblue;
        }
    }
    @keyframes shake {
        10%,
        90% {
            transform: translate3d(-5px, 0, 0);
        }

        20%,
        80% {
            transform: translate3d(5px, 0, 0);
        }

        30%,
        50%,
        70% {
            transform: translate3d(-5px, 0, 0);
        }

        40%,
        60% {
            transform: translate3d(5px, 0, 0);
        }
    }
    @keyframes title-appear {
        from {
            opacity: 0;
            /* font-size: 0px; */
            transform: scaleX(0);
        }
        to {
            opacity: 1;
            /* font-size: 40px; */
            transform: scaleX(1);
        }
    }

</style>