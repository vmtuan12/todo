<script>
    export default {
        data() {
            return {
                list: [],
                id: 0,
                title: '',
                description: ''
            }
        },
        methods: {
            addTodo() {
                
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
            }
        }
    }
</script>

<script setup>
import Card from '../UI/Card.vue';
import InputField from '../UI/InputField.vue';
import Input from '../UI/Input.vue';
import Button from '../UI/Button.vue';

</script>

<template>
    <InputField>
        <template #inputTitle>
            <Input v-model="title"/>
        </template>
        <template #inputDescription>
            <Input v-model="description"/>
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
            <template #heading>{{ item.title }}</template>
            <template #button>
                <Button @pressed="removeTodo(item.id)">Remove todo</Button>
            </template>
        </Card>
    </template>
</template>

<style scoped>
    input {
        border-radius: 10px;
        border: 2px solid black;
    }
    input:focus {
        background-color: antiquewhite;
    }
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