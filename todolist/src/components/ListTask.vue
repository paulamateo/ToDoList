<script setup lang="ts">
import { ref } from 'vue';

const props = defineProps(['todos'])
const newItem = ref('');

function addTask() {
    props.todos.push({
        name : newItem.value
    })
    newItem.value = ''
}

function onClick(id: number) {
    console.log(`click on task ${id}`);
}
</script>

<template>
    <div v-for="todo in todos">
        <input type="checkbox" name="" id=""> 
        {{ todo.name }}
        <button @click="onClick(todo.id)">X</button>
    </div>
</template>