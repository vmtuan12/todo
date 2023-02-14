<script>
    export default {
        data() {
            return {
                list: [],
                id: 0,
                title: ref('')
            }
        },
        methods: {
            addTodo(e) {
                const value = e.target.value.trim()
                console.log(value);
                if(value === "") {
                    return;
                }
                this.list.push({
                    id: this.id++,
                    title: value,
                    description: 'yeu ha phuong vl'
                })
                e.target.value = ''
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
import { remove } from '@vue/shared';
import { ref } from 'vue';
import Card from '../UI/Card.vue';
import InputField from '../UI/InputField.vue';

</script>

<template>
    <InputField>
        <template #input>
            <input placeholder="add a new task" @keyup.enter="addTodo"/>
        </template>
        <!-- <template #button>
            <button @click="greet" type="submit">add task</button>
        </template> -->
    </InputField>
    <template v-for="item in list" :key="item.id">
        <Card>
            <template #checked>
                <input type="checkbox" id="checkbox"/>
            </template>
            <template #heading>{{ item.title }}</template>
            <template #button>
                <button @click="removeTodo(item.id)">Remove todo</button>
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