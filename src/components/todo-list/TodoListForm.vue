<template>
    <div class="todo-list__action">
        <input
            v-bind:value="todoItem"
            type="text"
            class=""
            v-on:input="updateValue($event.target.value)"
        >

        <button
            class="todo-list__action__button"
            v-on:click="updateTodoItem()"
        >
            Add todo
        </button>
    </div>
</template>

<script setup>
import {ref} from 'vue'

const emit = defineEmits(['update:todo-item'])

const todoItem = ref('')

function updateValue(inputVal){
    todoItem.value = inputVal
}

function updateTodoItem(){
    emit('update:todo-item', todoItem.value)
    todoItem.value = ''
}


</script>